pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			sh """
  			yamllint service.yaml
     			"""
			}
                }
            }
        }
    }
