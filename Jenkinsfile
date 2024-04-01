pipeline {
    agent {
        docker {
            image 'python:3.9'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'python index.py bdist_wheel' 
            }
        }
    }
    
    post {
        success {
            archiveArtifacts artifacts: 'dist/*.whl', allowEmptyArchive: true
        }
    }
}
