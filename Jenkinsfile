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

        stage('Build'){
           
            steps {
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }

        }
    }
}