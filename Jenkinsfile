#!groovy

pipeline {

   environment 
   {
        TEST="welcome to jenkins"
   }
   agent nodeone
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
       
    post {
        failure
            {
                echo "failed"
            }
        }
}
