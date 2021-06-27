pipeline {
    agent any
        tools {
            maven 'Maven 3.8.1'
            jdk 'jdk11'
        }

    stages {
        stage ('Compile') {
            steps {
                 bat 'mvn clean install'
            }
        }
        stage ('Testing Stage') {
            steps {
                 bat 'mvn test -DBASE_URI=https://api.spotify.com -DACCOUNT_BASE_URI=https://accounts.spotify.com'
            }
        }
    }
}