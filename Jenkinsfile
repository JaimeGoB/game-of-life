pipeline{
    tools{
        jdk 'LocalJDK8'
        maven 'LocalMaven'
    }
    
    agent none
    
    stages{
        stage('Checkout'){
            agent any
            steps{
                git 'https://github.com/JaimeGoB/game-of-life.git'
            }
        }
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
