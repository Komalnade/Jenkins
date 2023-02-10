pipeline {
    agent any
    environment {
        name = 'komal'
    }
    parameters {
        string(name: 'person',defaultValue: 'komal nade',description: "who are you")
        booleanParam(name: 'isFemale',defaultValue: true,description: "")
        choice(name: 'City',choices: ['Mumbai','Pune','Bangalore'],description: "")
    }

    stages {
        stage('Run A Command') {
            steps {
                sh '''
                date
                ls
                pwd
                cal 2021
                '''
                
                
            }
        }
        stage('Environment Variables') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we should"
            }
            steps {
                echo 'deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        } 
    }
    post{
        always {
            echo "I will always say Hello again!"
        }
        failure {
            echo "Failure"
        }
        success {
            echo "Success"
        }
    }
}
