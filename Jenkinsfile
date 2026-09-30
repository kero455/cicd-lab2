pipeline {
    agent { label 'agent-01' }

    tools {
    jdk 'jdk-11'
    maven 'maven-3-5-4'
    }

    stages {

        
        stage('Build java app') {
            steps {
                sh 'mvn package install -DskipTests'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('build docker image') {
            steps {
                sh 'docker build -t my-java-app:ver1 .'
            }
        }
    }

    // post {
    //     success {
    //         echo 'Java Declarative Pipeline completed successfully!'
    //     }

    //     failure {
    //         echo 'Pipeline failed!'
    //     }

    //     always {
    //         echo 'Pipeline finished.'
    //     }
    // }
}