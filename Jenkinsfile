#!groovy
pipeline
{
    agent any

    tools {
        maven 'Maven'
        jdk 'jdk8'
    }

    stages

        {
        stage ('checkout'){
                git branch: 'master', credentialsId: '54ed9116-688e-44fe-a332-4f6f5bed6b65', url: 'https://github.com/georgeisacnewton/game-of-life.git'
        }
        stage ('Build')
        {
        steps
            {
                sh 'clean package'
            }
        }
        }
    post
    {
        success
        {
        junit 'target/surefire-reports/**/*.xml'
        }
    }
}
