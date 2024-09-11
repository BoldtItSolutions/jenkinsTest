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
                sh 'make || true' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }

        stage('Test') {
            steps {
                /* `make check` returns non-zero on test failures,
                * using `true` to allow the Pipeline to continue nonetheless
                */
                sh 'make check || true' 
                junit '**/target/*.xml' 
            }
        }
    }
}