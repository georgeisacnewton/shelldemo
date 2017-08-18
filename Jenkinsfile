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
        steps{
                git branch: 'master', credentialsId: '54ed9116-688e-44fe-a332-4f6f5bed6b65', url: 'https://github.com/georgeisacnewton/game-of-life.git'
        }}
        stage ('Build')
        {
        steps
            {
                sh 'mvn clean package'
                sh 'cat /etc/passwd > test.txt'
                stash includes: 'test', name: 'test'
            }
        
         post
             {
                 success
             {
              unstash 'test'
              sh 'cat test'
              }
            }
}     }  }
