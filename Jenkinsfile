pipeline{
    agent any
    parameters {
      string defaultValue: '1.0.1', description: 'Choose Your Git Tag', name: 'tag'
    }

    stages{
        stage("Param Demo"){
            steps{
                echo "Hi this is your tag ${tag}, Welcome to Jenkins"
            }
        }
    }
}
