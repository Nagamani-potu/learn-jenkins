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
        timeout(time: 1, unit: 'SECONDS')
    }
    //build
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
                    echo  "Here I wrote shell script"
                    echo "$GREETING"
                """
            }
        }
    }

    //post build
    post {
        always {
            echo 'I will always say Hello again'
        }
        failure {
            echo 'This will run when pipeline is failed, used generfally to send some alerts'
        }
        success {
            echo 'I will say Hello again when pipeline is success'
        }
    }
}

