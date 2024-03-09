pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Compile the .cpp file using a shell script
                sh 'g++ -o PES1UG21CS271 BUILDTESTDEPLOYFILE.cpp'
            }
        }
        stage('Test') {
            steps {
                // Print output of the .cpp file using a shell script
                sh './PES1UG21CS271'
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps if necessary
               echo 'Deployment successful'
            }
        }
    }
    
    post {
        always {
            // Display 'pipeline failed' in case of any errors within the pipeline
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
