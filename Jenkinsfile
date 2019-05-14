pipeline {
    agent none
    stages {
        stage('Build Image') {
            steps {
                agent any
                script {
                    def base
                    base = docker.build("test-app")
                    }
                    sh 'echo "WOOOOO Image Built"'
                }
            }

        stage('Run Image') {
            /* Ideally, we would run a test framework against our image.
             * For this example, we're using a Volkswagen-type approach ;-) */
            steps{
            sh 'docker run -it -p 80:3000'
            sh 'echo "Successfully Running Containter!"'
            }
        }

        stage('Ping Express Server'){
            steps{
            sh 'curl http://0.0.0.0:80'
            sh 'echo "Successful Ping!"'
            }
        }

        stage('Stop Container'){
            steps{
            sh 'docker kill $(docker ps -q)'
            }
        }
    }
}