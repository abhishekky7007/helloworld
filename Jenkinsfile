pipeline {
    agent {
        docker {
            image 'openjdk:17-jdk'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from version control
                git 'https://github.com/abhishekky7007/helloworld.git'
            }
        }
        stage('Build') {
            steps {
                // Compile the Java code
                sh 'javac HelloWorld.java'
            }
        }
        stage('Test') {
            steps {
                // Run any tests (if you have tests)
                sh 'java HelloWorld'
            }
        }
        stage('Package') {
            steps {
                // Package the application (if applicable)
                sh 'jar cf hello-world.jar HelloWorld.class'
            }
        }
    }
    post {
        always {
            // Clean up workspace after build
            cleanWs()
        }
    }
}
