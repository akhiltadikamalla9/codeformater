pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
		def yamllintPath = "${WORKSPACE}" 
		echo "${WORKSPACE}"
		def directory = new File(".")
		directory.eachFile { file ->
		  if (file.name.endsWith(".yaml") || file.name.endsWith(".yml")) {
		    def command = [yamllintPath, options, file.absolutePath]
		    // Print command (optional for debugging)
		    println "Running command: ${command.join(' ')}"
		    def process = command.execute()
		    // Print output stream
		    process.inputStream.eachLine { line ->
		      println line
		    }
		}
                }
            }
        }
    }
