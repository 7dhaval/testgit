pipeline {
    agent any
    
    stages {
        stage("Clone") {
            steps {
                // Clone the repository
                git 'https://github.com/your-username/your-repo.git'
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
                sh 'git add .'
                sh 'git commit -m "Jenkins pipeline commit"'
                sh 'git push origin master'
            }
        }
    }
}
