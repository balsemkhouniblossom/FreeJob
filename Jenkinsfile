pipeline {
    agent any

    triggers {
        pollSCM('H/1 * * * *')  // Check Git repository every minute
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/your-repo.git'
            }
        }

        stage('Display Date') {
            steps {
                script {
                    def currentDate = new Date()
                    echo "Current System Date: ${currentDate}"
                }
            }
        }
    }
}
