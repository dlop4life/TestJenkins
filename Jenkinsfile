node ('mac') {
stage('Build Image') {
    steps {

            def base
            base = docker.build("test-app")

            sh 'echo "WOOOOO Image Built"'
        }
    }
    }