pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
	sh """
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
