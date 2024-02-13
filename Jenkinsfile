pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			  // Define directory containing YAML files
			  def directory = ${WORKSPACE} // Replace with actual path
			
			  // Set options for yamllint (optional)
			  def options = ["--config=.yamllint"] // Modify options as needed
			
			  // Get yamllint executable from tools section (if installed)
			  def yamllint = sh(returnStdout: true, script: "which yamllint").trim()
			
			  if (yamllint) {
			    // Loop through each YAML file in the directory
			    directory.eachFile { file ->
			      if (file.name.endsWith(".yaml") || file.name.endsWith(".yml")) {
			        def command = "${yamllint} ${options} ${file.absolutePath}"
			        echo "Running yamllint on ${file.name}:"
			        sh(command: command)
			      }
			    }
			  } else {
			    echo "yamllint not found. Skipping YAML linting."
			  }
                }
            }
        }
    }
    }
}
