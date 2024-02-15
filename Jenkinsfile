pipeline { 
    agent {
        node {
            label 'AGENT-1'
            }
    } 
    environment {
        GREETING = 'Hello Jenkins,How are you'
    }
    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                    echo "Here I wrote hi hello dfdfshell script"
                    echo  "$GREETING"
                    echo  "$GREETING"
                    #sleep 10
                """
            }
        }
        stage('check params') {
            steps {
                sh """
                    echo " Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
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