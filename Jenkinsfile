pipeline {
    steps {
        step('Build Image') {
                /* This builds the actual image; synonymous to
                 * docker build on the command line */

                sh 'docker build -t test-app .'
                sh 'echo "Image Successfully Built'
            }

        step('Run Image') {
            /* Ideally, we would run a test framework against our image.
             * For this example, we're using a Volkswagen-type approach ;-) */

            sh 'docker run -it -p 80:3000'
            sh 'echo "Successfully Running Containter!"'

        }

        step('Ping Express Server'){
            sh 'curl http://0.0.0.0:80'
            sh 'echo "Successful Ping!"'

        }

        step('Stop Container'){
            sh 'docker kill $(docker ps -q)'
        }
    }
}