pipeline {
    agent any
	parameters {
        string defaultValue: '1.0.1', description: 'Choose Your Git Tag', name: 'tag'
         }
    
    stages {
        stage("Clone") {
            steps {
                // Clone the repository
                git 'https://github.com/7dhaval/testgit.git'
            }
        }
        
        stage("Build") {
            steps {
                // Build your code or perform any necessary actions
                // For demonstration purposes, we'll simply echo a message
                echo "Building code..."
            }
        }
        
        stage("Push") {
            steps {
                // Push the code to the remote repository
                sh 'git tag ${tag}'
                sh 'git push origin main'
            }
        }
    }
}
