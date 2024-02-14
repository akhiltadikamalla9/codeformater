pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			// Define the target directory
			def dir = new File("${WORKSPACE}")
			echo "${WORKSPACE}"
			sh 'ls'
			// Iterate through all files (recursively by default)
			dir.eachFile { file ->
			println "Processing file: ${file.name}"
			if (file.name.endsWith(".yaml") || file.name.endsWith(".yml")) {
			echo "11111111111111111111111"
			  // Access and process the file here
			  println "Processing file: ${file.name}"
			  sh 'yamllint ${file.name}"'
			echo "22222222222222222"
			}
			}
            }
        }
    }
    }
}
