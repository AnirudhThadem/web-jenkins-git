pipeline {
    agent any
    tools {
        maven 'maven_3_5_0'
    }

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn clean install'

                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn test'
                }
            }
        }
        stage ('Deploy Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
	  bat'mvn package'
	deploy adapters: [tomcat8(credentialsId: 'df450cbb-11fb-48e5-b2a7-51e2ea0d0f39', path: '', url: 'http://localhost:8081/')], contextPath: 'webgit', war: '**/*.war'
 }
            }
        }


    }
}
