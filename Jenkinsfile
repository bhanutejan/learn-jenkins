pipeline { 
    agent {
        node {
            label 'AGENT-1'
            }
    } 
    stages {
        stage('Development') { 
            steps { 
                echo 'Hello Development' 
            }
        }
        stage('QA') { 
            steps { 
                echo 'Hello QA' 
            }
        }
        stage('Prod') { 
            steps { 
                echo 'Hello Production' 
            }
        }
    }
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