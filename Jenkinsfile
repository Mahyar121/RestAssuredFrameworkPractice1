node {
    agent any

    stages {
        stage('SCM Checkout') {
            git 'https://github.com/Mahyar121/RestAssuredFrameworkPractice1'
        }

        stage('Compile stage') {
            steps {
            def mvnHome = tool name: 'maven_3_8_1', type: 'maven'
                    sh "${mvnHome}/bin/mvn package"

            }
        }

        stage ('Testing Stage') {
            steps {
                def mvnHome = tool name: 'maven_3_8_1', type: 'maven'
                    sh '${mvnHome}/bin/mvn test -DBASE_URI=https://api.spotify.com -DACCOUNT_BASE_URI=https://accounts.spotify.com'
            }
        }
    }
}