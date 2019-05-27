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

      stage ('Deploy') {

            steps {

                sh 'ssh root@192.168.1.101 rm -fR ${TOMCAT_HOME}/webapps/RestDemo-0.0.1*

                sh 'ssh root@192.168.1.101 ls ${TOMCAT_HOME}/webapps/'

                sh 'scp target/RestDemo-0.0.1-SNAPSHOT.war root@192.168.1.101:${TOMCAT_HOME}/webapps/'

            }

        }

    }
}



