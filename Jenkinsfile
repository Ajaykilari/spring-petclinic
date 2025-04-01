pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker build -t spring-petclinic .'
                sh 'docker run -d -p 8080:8080 spring-petclinic'
            }
        }
    }
}

