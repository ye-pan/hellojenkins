pipeline {
    agent { docker 'maven' }
    stages {
        stage('version') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('build') {
            steps{
                sh 'mvn -DskipTests clean package'
            }
        }
    }
}