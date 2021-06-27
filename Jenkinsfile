pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            git 'https://github.com/Mahyar121/RestAssuredFrameworkPractice1'
        }

        stage('Compile stage') {
        def mvnHome = tool name: 'maven_3_8_1', type: 'maven'
            steps {

                    sh "${mvnHome}/bin/mvn package"

            }
        }

        stage ('Testing Stage') {
        def mvnHome = tool name: 'maven_3_8_1', type: 'maven'
            steps {

                    sh '${mvnHome}/bin/mvn test -DBASE_URI=https://api.spotify.com -DACCOUNT_BASE_URI=https://accounts.spotify.com'
            }
        }
    }
}