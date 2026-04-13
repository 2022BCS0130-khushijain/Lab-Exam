pipeline {
    agent {
        docker {
            image 'python:3.10-slim'
        }
    }

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip install --no-cache-dir -r requirements.txt'
            }
        }

        stage('Train Model') {
            steps {
                sh 'python train.py'
            }
        }

        stage('Student Info') {
            steps {
                echo 'Student: Khushi Jain | Roll No: 2022BCS0130'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'model.pkl, metrics.json', fingerprint: true
            }
        }
    }
}