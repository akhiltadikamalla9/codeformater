pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
			// Define the target directory
			def baseDir = new File("${WORKSPACE}")
			echo "${WORKSPACE}"
			sh 'ls'
			sh 'find . -name "**.yaml" | xargs yamllint -'
			
            }
        }
    }
    }
}
