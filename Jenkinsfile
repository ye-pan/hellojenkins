pipeline {
    agent { docker 'maven' }
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
                    junit 'build/reports/**/*.xml'
                }
            }
        }
    }
}