#!groovy

pipeline {

   environment 
   {
        TEST="welcome to jenkins"
   }
   agent none
   stages {

        stage ('test')
        {
            steps   { 
             echo 'Hello first script'
            } 
       }
        node {
        stage ('build')
        {
            steps   {
                    sh 'cat /etc/passwd'
               }
        }
        
        stage ('fail')
        {
            steps    { 
                
                sh 'echo ${TEST}'
                
                }
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
