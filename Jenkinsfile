pipeline{

    agent any

    tools{
        maven 'MAVEN'
    }

    stages{

        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Sunera25/jenkins-docker-example.git']])
                sh'''
                    mvn -Dmaven.failure.ignore=true clean package
                '''
            }
        }

        stage('Build Docker Image'){
            steps{
                script{
                    sh '''
                        docker build -t sunera25/my-app-1.0 .
                    '''
                }
            }
        }
    }
}