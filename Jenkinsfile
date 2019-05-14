pipeline {
    agent {
        docker 'node'
    }

    stages {
        stage('Build Image') {
                /* This builds the actual image; synonymous to
                 * docker build on the command line */
            steps{
                sh 'docker build -t test-app .'
                sh 'echo "Image Successfully Built'
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