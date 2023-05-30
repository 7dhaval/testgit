pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Your build steps here
            }
        }

        stage('Test') {
            steps {
                // Your test steps here
            }
        }

        stage('Deploy') {
            steps {
                // Your deployment steps here
            }
        }
    }

    post {
        always {
            // Generate random parameter
            def randomParam = java.util.UUID.randomUUID().toString()

            // Tag the repository
            script {
                gitTag(tagName: randomParam, message: "Random parameter tag")
            }

            // Push the changes
            script {
                gitPush()
            }
        }
    }
}
