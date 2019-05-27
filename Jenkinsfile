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

       stage('Code Coverage') {

          steps {

        junit '*/build/test-results/*.xml'

        step( [ $class: 'JacocoPublisher' ] )

     }

        }

    }
}



