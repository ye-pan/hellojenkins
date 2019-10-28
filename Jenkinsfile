pipeline {
    agent {
        docker {
            image 'maven'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('version') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('build') {
            steps {
                sh 'mvn -DskipTests clean package'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}