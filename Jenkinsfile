 pipeline{
    agent any 
    tools {
        maven 'Maven'
    }
    stages{
        stage("Test"){
            steps{
                // mvn test
                sh "mvn test"
    
            }

        }
            stage("build"){
            steps{
                // mvn package
                sh "mnv package"
                
            }

        }
        stage("Deploy on Test"){
            steps{
                // deploy on container -> plugin
                deploy adapters: [tomcat9(credentialsId: 'tomcatserverdetails1', path: '', url: 'http://15.206.28.52:8085')], contextPath: '/app', war: '**/*.war'
                
            }

        }
        stage("Deploy on Prod"){
            steps{
                // deploy on container -> plugin
                deploy adapters: [tomcat9(credentialsId: 'tomcatserverdetails1', path: '', url: 'http://43.205.114.163:8085')], contextPath: '/app', war: '**/*.war'
                
            }
        }

        }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
