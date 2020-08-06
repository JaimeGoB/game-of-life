pipeline{
    tools{
        jdk 'LocalJDK8'
        maven 'LocalMaven'
    }
    
    agent none
    
    stages{
        stage('Compile'){
            agent any
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            agent any
            steps{
                sh 'mvn test'
            }
            post{
                always{
                    junit 'gameoflife-web/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Package'){
            agent any
            steps{
                sh 'mvn package'
            }
        }
    }
}
