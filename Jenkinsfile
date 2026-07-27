pipeline {

    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/SShifa/e-commerce-fullstack_springboot_angular_aws.git'
            }
        }


        stage('Build Backend') {
            steps {
                sh '''
                cd e-commerce-backend
                mvn clean package
                '''
            }
        }


        stage('Test') {
            steps {
                sh '''
                cd e-commerce-backend
                mvn test
                '''
            }
        }


        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'e-commerce-backend/target/*.jar'
            }
        }

    }
}
