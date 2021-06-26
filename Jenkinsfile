pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_8_1') {
                    sh '${MAVEN_HOME}/bin/mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_8_1') {
                    sh '${MAVEN_HOME}/bin/mvn test'
                }
            }
        }
    }
}