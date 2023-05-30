pipeline {
    agent any
    parameters {
        string defaultValue: '1.0.1', description: 'Choose Your Git Tag', name: 'tag'
    }

    stages {
        stage("Param Demo") {
            steps {
                echo "Hi, this is your tag ${params.tag}, Welcome to Jenkins"
            }
        }

        stage("Push Tag") {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'githu', usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]) {
                        sh "git tag ${params.tag}"
                        sh "git -v push https://7dhaval@github.com/testgit ${params.tag}"
                    }
                }
            }
        }
    }
}
