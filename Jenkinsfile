pipeline {
    agent any

    tools {
        // Define the Maven tool with the name 'Maven' in Jenkins
        maven 'Maven'
    }

    stages {
        stage('Initialize') {
            steps {
                script {
                    // Print environment variables for debugging
                    echo "PATH = ${env.PATH}"
                    echo "M2_HOME = ${env.M2_HOME}"
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Update the Maven War Plugin version
                    def mavenWarPluginVersion = '3.3.1'

                    // Run Maven build with clean and package goals
                    sh "mvn clean package"

                    // Alternatively, you can specify the version in the POM file
                    // sh "mvn clean package -Dmaven.war.plugin.version=${mavenWarPluginVersion}"
                }
            }
        }
    }
}
