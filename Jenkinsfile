pipeline {
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
                    sh 'cat /etc/passwd'
               }
        }
        stage ('fail')
        {
            steps    { 
                
                sh 'date'
                
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
