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
}