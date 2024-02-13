pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			  // Define directory containing YAML files
			  def directory = ${WORKSPACE} // Replace with actual path
			  // Get yamllint executable from tools section (if installed)
			  // Loop through each YAML file in the directory
			    directory.eachFile { file ->
			      if (file.name.endsWith(".yaml") || file.name.endsWith(".yml")) {
			        def command = "${yamllint} ${options} ${file.absolutePath}"
			        echo "Running yamllint on ${file.name}:"
			        sh(command: command)
			      }
			    }
            }
        }
    }
    }
}
