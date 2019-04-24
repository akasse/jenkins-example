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
        stage('SCM Checkou') {
             git 'https://github.com/akasse/jenkins-example/edit/master/Jenkinsfile'
        }
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
