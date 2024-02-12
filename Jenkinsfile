pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
def yamllintPath = "${WORKSPACE}" 
// Replace with your actual path
// Define directory containing YAML files (optional, defaults to current)
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
    // Check exit code and handle errors
    def exitCode = process.waitFor()
    if (exitCode != 0) {
      println "Error: yamllint failed with exit code ${exitCode}"
    }
  }
}
		}
                }
            }
        }
    }
