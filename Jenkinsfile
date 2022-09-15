pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/n1032658/java-maven-junit-helloworld.git'
                sh 'mvn clean compile'
                
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                
            }
            
            stage('verfiy') {
            steps {
                sh 'mvn verify'
                
            }}

            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
    }
}
