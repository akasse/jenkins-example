pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
             def mvnHome = tool name: 'Maven', type: 'maven'
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh '${mvnHome}/bin/mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {
            def mvnHome = tool name: 'Maven', type: 'maven'
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh '${mvnHome}/bin/mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            def mvnHome = tool name: 'Maven', type: 'maven'
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh '${mvnHome}/bin/mvn deploy'
                }
            }
        }
    }
}
