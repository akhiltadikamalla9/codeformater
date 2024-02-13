pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			// Define the target directory
			def dir = new File("${WORKSPACE}")
			
			// Iterate through all files (recursively by default)
			dir.eachFile { file ->
			  // Access and process the file here
			  println "Processing file: ${file.name}"
			}
            }
        }
    }
    }
}
