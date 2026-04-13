pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
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
                archiveArtifacts artifacts: 'model.pkl,metrics.json', fingerprint: true
            }
        }
    }
}
