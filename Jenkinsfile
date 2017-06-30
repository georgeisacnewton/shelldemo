#!groovy

pipeline {

   environment 
   {
        TEST="welcome to jenkins"
   }
   agent any

   stages {

        stage ('test')
        {
            steps   { 
             echo 'Hello first script'
            } 
       }
        stage ('build')
        {
            steps   {
                    sh 'cat /etc/passwd > test'
               }
        }
        
        stage ('fail')
        {
            steps    { 
                
                sh 'echo ${TEST}'
                
                }
            }
                }
       
    post {
        failure
            {
                echo "failed"
            }
        }
}
