pipeline {
    agent any


    stages {
        stage('Checkout') { 
            steps {
                git branch: 'main', url: 'https://github.com/erVaibhs/spring-petclinic.git'

            }
        }
        stage('Build') {
            steps {
                sh "./mvnw clean package"
            }


        }
    }

                post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
}
