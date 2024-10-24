pipeline {
    agent any

    stages {
        stage ('GetProject') {
            steps {
                // Cloning the Git repository
                git 'https://github.com/damienb1983/CT5171_test1Maven.git'
            }
        }
        stage ('Build') {
            steps {
                // Running Maven build
                sh 'mvn clean compile dependency:copy-dependencies'
            }
        }
        stage ('Exec') {
            steps {
                // Executing the Java application using Maven
                sh 'mvn exec:java'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully.'
        }
        failure {
            echo 'Build failed!'
        }
    }
}