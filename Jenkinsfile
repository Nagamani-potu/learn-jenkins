pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }

    environment {
        GREETINGS = 'Hello Jenkins'
    }

    options {
        timeout(time: 1, unit: 'HOURS')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }

        stage('Deploy') {
            steps {
                sh """
                    echo "Here I wrote shell script"
                    echo "$GREETINGS"
                """
            }
        }
    }

    post {
        always {
            echo 'I will always say Hello again'
        }
        failure {
            echo 'This will run when pipeline is failed, used generally to send some alerts'
        }
        success {
            echo 'I will say Hello again when pipeline is successful'
        }
    }
}

