pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
	// Define directory and optional filter (e.g., by filename pattern)
          def directory = "${WORKSPACE}"
          def filter = "*.yaml" // Optional: Filter files (e.g., ".specific-folder/*.yaml")

          // Initialize empty map to collect yaml contents (optional)
          def yamlContents = [:]

          // Get all YAML files using glob with optional filter
          def yamlFiles = dir(directory) {
            glob(filter ?: "*.yaml")
          }

          // Loop through each file
          for (file in yamlFiles) {
            echo "Processing file: ${file.name}"

            // Read YAML content using YAMLSlurper (from Groovy 3.x)
            if (GroovySystem.groovyMajorVersion >= 3) {
              def content = new YamlSlurper().parseText(file.text)
            } else {
              // Use Snakeyaml for Groovy versions below 3.x
              @Grab('org.yaml:snakeyaml:1.17')
              def parser = new Yaml()
              def content = parser.load(file.text)
            }

            // Store content in map or process directly (optional)
            yamlContents[file.name] = content

            // Example processing step: Access specific parameter
            if (content.containsKey("key")) {
              def someParam = content["key"]
              echo "Value of 'key': ${someParam}"
            } else {
              echo "Key 'key' not found in this file."
            }
          }
		}
                }
            }
        }
    }
