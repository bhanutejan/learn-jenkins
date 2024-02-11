pipeline { 
    agent {
        node {
            label 'AGENT-1'
            }
    } 
    environment {
        GREETING = 'Hello Jenkins'
    }
    //build
    stages {
        stage('Build') { 
            steps { 
                echo 'Hello Build' 
            }
        }
        stage('Test') { 
            steps { 
                echo 'Hello Test' 
            }
        }
        stage('Deploy') { 
            steps { 
                echo 'Hello Deploy' 
                sh """
                    echo "Here I wrote shell script"
                    env
                """
            }
        }
    }
    // post build
    post {
        always {
            echo 'I wll always say Hello Again..!'
        }
        failure {
            echo 'this runs when pipeline is failsed, user generally to send some alerts'
        }
        success {
            echo 'I will say Hello when pipeline is success'
        }
    }
}