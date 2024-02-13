pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			  // Define directory containing YAML files
			  def directory = ${WORKSPACE} // Replace with actual path
			   directory.traverse { file ->
			   if (file.name.endsWith(".yaml") || file.name.endsWith(".yml")) {
			    // Process the file here
			    println "Found YAML file: ${file.name}"
			      }
			    }
            }
        }
    }
    }
}
