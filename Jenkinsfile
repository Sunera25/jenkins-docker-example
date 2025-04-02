pipeline{

    agent any

    tools{
        mave 'MAVEN'
    }

    stages{

        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Sunera25/jenkins-docker-example.git']])
                sh'''
                    mvn -Dmaven.failure.ignore=true clan package
                '''
            }
        }
    }
}