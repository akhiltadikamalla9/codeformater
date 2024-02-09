pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			sh """
    			yamllint -f yaml service.yaml
  			"""
			}
                }
            }
        }
    }
