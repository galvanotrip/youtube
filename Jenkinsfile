pipeline {
    agent any

    parameters {
        string(name: 'URL', defaultValue: '', description: 'Enter the video URL to download')
    }

    stages {
        stage('🧾 Show Parameters') {
            steps {
                echo "Received URL: ${params.URL}"
            }
        }

        stage('🚀 Run Downloader') {
            steps {
                sh 'python3 main.py "$URL"'
            }
        }
    }
}