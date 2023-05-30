pipeline {
    agent any
       parameters {
             string defaultValue: '1.0.1', description: 'Choose Your Git Tag', name: 'tag'
         }
    stages {
        stage("Build") {
            steps {
                // Build your code or perform any necessary actions
                // For demonstration purposes, we'll simply echo a message
                echo "Building code..."
            }
        }
        
        stage("Push") {
            steps {
		 withCredentials([usernamePassword(credentialsId: 'yoyo', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]){
                // Push the code to the remote repository
                sh 'git checkout main' // Switch to the main branch
                sh 'git tag ${tag}' // Create a new tag
                sh 'git push origin ${tag}' // Push the tag to the remote repository
		}
            }
        }
    }
}
