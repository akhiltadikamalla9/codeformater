pipeline{
    agent any 
    stages {
    stage('Yaml file formatter') {
            steps {
                script {
	sh """
            # Find all YAML files in a specific directory
            find ${WORKSPACE}/codeformatter -maxdepth 1 -name "*.yaml" | while read file; do
            echo "Processing file: $file"

            # Process the YAML file using your preferred tool here, e.g., yamllint
            yamllint $file

            # Or process the content using tools like yq or jq
            # value="$(yq '.key' $file)"
            # echo "Value of 'key': $value"
          done
        """
			}
                }
            }
        }
    }
