pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo "displayName: $currentBuild.displayName"
                echo "number: $currentBuild.number"
            }
        }
    }
}