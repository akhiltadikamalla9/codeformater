pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			// Define the target directory
			def dir = new File("${WORKSPACE}")
			echo "${WORKSPACE}"
			// Iterate through all files (recursively by default)
			dir.eachFile { file ->
			echo "11111111111111111111111"
			  // Access and process the file here
			  println "Processing file: ${file.name}"
			echo "22222222222222222"
			}
            }
        }
    }
    }
}
