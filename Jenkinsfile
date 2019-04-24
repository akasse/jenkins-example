 def mvnBuild() {
     mvn: ${MAVEN}/bin/mvn
    }

pipeline {
    agent any
    
    options {
     timeout(time: 120, unit: 'MINUTES')
    }
    
   
    
    environment {
      MAVEN = tool name: 'Maven', type: 'maven'
      MVN = mvnBuild().mvn
    }
    
    

    stages {
        stage('Check Scm Changelog') {
          steps {
             git 'https://github.com/akasse/jenkins-example/edit/master/Jenkinsfile'
          }
        }
        stage ('Clean Package') {
            steps {
                 sh '${MVN} clean package'
            }
        }
        stage ('Unit tests') {
            steps {
                    sh '${MVN} clean test'
            }
        }
    }
    
    
    
    
}
