pipeline {
    agent any

    stages {
        stage ('Checkout Codebase') {
            steps {
            cleanWs()
            checkout scm: [$class: 'GitSCM', branches: [[name: '*/master']]]
            }
        }

        stage('Build') {
            steps {
                 withMaven(maven : 'maven_3_8_1') {
                    sh '${MAVEN_HOME}/bin/mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven_3_8_1') {
                    sh '${MAVEN_HOME}/bin/mvn test -DBASE_URI="https://api.spotify.com" -DACCOUNT_BASE_URI="https://accounts.spotify.com"'
                }
            }
        }
    }
}