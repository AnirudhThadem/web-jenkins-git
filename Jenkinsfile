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
	deploy adapters: [tomcat9(credentialsId: '66c38397-fa8f-4d92-ac16-361cd217042c', path: '', url: 'http://localhost:9090/')], contextPath: 'sample-git', war: '**/*.war'
	}
            }
        }


    }
}
