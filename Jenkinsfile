#!groovy
pipeline
{
    agent any

    triggers { pollSCM('* 0 0 0 0') }

    tools {
        maven 'Maven'
        jdk 'jdk8'
    }

    stages

        {

        stage ('checkout'){
        steps{
                git branch: 'master', credentialsId: '54ed9116-688e-44fe-a332-4f6f5bed6b65', url: 'https://github.com/georgeisacnewton/game-of-life.git'
        }}
        stage ('Build')
        {
        steps
            {
                sh 'mvn clean package'
                sh 'cp *.xml $WORKSPACE' 

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
