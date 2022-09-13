pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
        stage('Test') {
            when {
                anyOf {
 		     branch 'develop';
		     branch 'main'
                }
            }
            steps {
                sh './gradlew test'
            }
        }
        stage('Deploy') {
 	    when {
		branch 'main'
            }
            steps {
                echo "Deploy"
            }
        }
    }
}
