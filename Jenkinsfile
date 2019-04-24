
pipeline {
    agent any
    
    options {
     timeout(time: 120, unit: 'MINUTES')
    }
    
   
    
    environment {
      MAVEN = tool name: 'Maven', type: 'maven'
    }
    
    

    stages {
        stage('INFO') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        
        stage('Check Scm Changelog') {
          steps {
             echo 'Git Checkout'
              checkout scm
          }
        }
        stage ('Clean Package') {
            steps {
                 sh '${MAVEN}/bin/mvn clean package'
            }
        }
        stage ('Unit tests') {
         
            steps {
                 sh '${MAVEN}/bin/mvn clean test'
            }
         
            post {
               success {
                 echo 'Unit tests execution finished'
               }
           }
        }
    }
    
    
    
    
}
