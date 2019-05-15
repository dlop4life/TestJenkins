node ('mac') {
stage('Build Image') {
    steps {
        agent any

            def base
            base = docker.build("test-app")

            sh 'echo "WOOOOO Image Built"'
        }
    }
    }