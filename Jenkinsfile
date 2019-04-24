pipeline {
    agent any
    
    options {
     timeout(time: 120, unit: 'MINUTES')
    }
    
    environment {
      MAVEN = tool name: 'Maven', type: 'maven'
      MVN = ${MAVEN}/bin/mvn
    }

    stages {
        stage ('Compile Stage') {
            steps {
                 sh '${MVN} clean compile'
            }
        }
        stage ('Testing Stage') {
            steps {
                    sh '${MVN} test'
            }
        }
    }
    
    
}
