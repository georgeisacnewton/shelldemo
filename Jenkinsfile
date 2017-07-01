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
                git branch: 'master', credentialsId: '365f08bf-6843-4c5b-8810-1b305dd38907', url: 'https://github.com/georgeisacnewton/game-of-life.git'
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
