pipeline {
    agent any 
    stages {
        stage('Build') {  // feature/* develop main
            steps {
                sh './gradlew build'
            }
        }
        stage('Test') {  // develop main
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
        stage('Deploy') { // main
 	    when {
		branch 'main'
            }
            steps {
                echo "Deploy"
            }
        }
    }
}

/*
4. Hoppa till feature/jenkins-config och committa nya directives i Jenkinsfile
5. Pusha till Github (feature/jenkins-config med Ny Jenkinsfile)
6. Merga in feature/jenkins-config i develop och pusha
7. Scan multibranch
8. Merga in develop i main och pusha
9. Scan multibranch
*/
