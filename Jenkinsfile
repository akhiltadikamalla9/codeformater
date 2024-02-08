pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
   def formatYaml(${WORKSPACE}/codeformatter) {
  // Read the YAML content
  def yamlData = readYaml file: filePath
  // Choose your formatting method:
  // 1. External formatter (requires installation)
  def formattedData = sh(returnStdout: true, script: 'yamllint -f yaml -', input: yamlData).trim()
  // 2. Basic Groovy string manipulation
  // def formattedData = yamlData.toString().replaceAll(/\n\s+/, '\n') // Adjust regex for your needs
  // 3. Advanced Groovy logic with external library (optional)
  //def formattedData = processWithYamlLibrary(yamlData) // Example using an external library
  // Write the formatted data back to the file
  writeFile file: filePath, text: formattedData
  // Log success message
  echo "Formatted YAML file: ${filePath}"
}
// Specify YAML files to format (relative paths from workspace)
def yamlFiles = ["path/to/file1.yaml", "path/to/file2.yaml", ...]
// Iterate over each file and format it
yamlFiles.each { filePath ->
  formatYaml(filePath)
}
			}
                }
            }
        }
    }
