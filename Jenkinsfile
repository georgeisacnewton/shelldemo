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

                    steps {
                 parallel (master:
                     {
                    node ('master')
                    {
                            sh 'echo ${TEST}'
                     }  
                     },              
                    slave:
                       {
                    node ('nodeone'){
                               sh 'echo ${TEST}; printenv'                      

                         }
                         })
                         }
                 }
                stage ('deploy')
                {steps{ echo ${env.branch}

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
