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
	}
            }
        }


    }
}
