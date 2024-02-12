pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
	sh """
 	     echo "1111111111111111111111111111111111111111111111111111"
	    find ${WORKSPACE} -maxdepth 1 -name "*.yaml" | while read file; do
            echo "Processing file: $file"
            yamllint $file
            done     
        """
			}
                }
            }
        }
    }
