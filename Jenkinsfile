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
