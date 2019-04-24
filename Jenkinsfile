pipeline {
    agent any
    
    options {
     timeout(time: 120, unit: 'MINUTES')
    }
    
    environment {
    MAVEN = tool name: 'Maven', type: 'maven'
    }

    stages {
        stage ('Compile Stage') {
             
            steps {
                
                    sh '${MAVEN}/bin/mvn clean compile'
               
            }
        }

        stage ('Testing Stage') {
           
            steps {
           
                    sh '${MAVEN}/bin/mvn test'
              
            }
        }


        stage ('Deployment Stage') {
            
            steps {
                
                    sh '${MAVEN}/bin/mvn deploy'
                
            }
        }
    }
}
