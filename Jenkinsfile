pipeline {
    agent any

    parameters {
        string(name: 'URL', defaultValue: '', description: 'Enter video URL to download')
    }

    stages {
        stage('🧪 Create venv and install deps') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('🚀 Run script with URL') {
            steps {
                sh '''
                    . venv/bin/activate
                    python main.py "$URL"
                '''
            }
        }
    }
}