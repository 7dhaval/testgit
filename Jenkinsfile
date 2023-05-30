pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/master']],
                          userRemoteConfigs: [[url: 'https://github.com/7dhaval/testgit']]])
            }
        }

        stage("Build and Test") {
            steps {
                // Perform your build and test steps here
            }
        }

        stage("Push Tag") {
            steps {
                script {
                    def tag = "1.0.4" // Replace with your desired tag or use params.tag

                    withCredentials([usernamePassword(credentialsId: 'githu', usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]) {
                        sh "git tag ${tag}"
                        sh "git push origin ${tag}"
                    }
                }
            }
        }
    }
}
