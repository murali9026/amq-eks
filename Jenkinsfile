pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Pull the code (including Dockerfile) from the GitHub repository
                git 'https://github.com/murali9026/amq-eks'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build the Docker image using the Dockerfile
                script {
                    docker.build('hello-world-image')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                // Run the Docker container to print "Hello, World!"
                script {
                    docker.image('hello-world-image').inside {
                        sh 'echo "Hello, World!"'
                    }
                }
            }
        }
    }
}
