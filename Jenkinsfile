pipeline {
    agent any

    parameters {
        string(name: 'URL', defaultValue: '', description: 'Enter the video URL to download')
    }

    stages {
        stage('🧪 Setup Python environment') {
            steps {
                sh '''
                    echo "🔧 Creating virtual environment..."
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('🚀 Download video') {
            steps {
                sh '''
                    echo "🎯 Downloading from URL: $URL"
                    . venv/bin/activate
                    python main.py "$URL"
                '''
            }
        }

        stage('📂 Move to SMB folder') {
            steps {
                sh '''
                    echo "📦 Moving .mp4 files to /var/smb/"
                    ls -lh *.mp4 || echo "⚠️ No .mp4 files found"
                    [ -f *.mp4 ] && mv *.mp4 /var/smb/ || echo "⚠️ Nothing to move"
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully. Video is available in /opt/smb.'
        }
        failure {
            echo '❌ Pipeline failed. Check the logs and verify the video URL.'
        }
        always {
            echo 'ℹ️ Pipeline finished.'
        }
    }
}