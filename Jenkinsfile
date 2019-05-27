pipeline {

    agent any

    stages {

        stage('SCM') {

            steps {
                    git "https://github.com/jadhavrachana/pipe_nexus.git"
                //
            }
        }

        stage('Test') {

            steps {
                    sh "mvn test"
                //
            }
        }

        stage('code analysis') {

            steps {
                    sh "/sonar_scanner/bin/sonar-scanner"
                //
            }
        }

        stage('artifact uploader') {

            steps {
                    sh "mvn clean deploy"
                //
            }
       }

       stage('Deploy2') {

            steps {
                  echo "this is step1"
                //
            }

        }

    }
}



