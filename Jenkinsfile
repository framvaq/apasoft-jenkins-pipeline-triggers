pipeline {
    agent any
    // Check for changes in the SCM every minute
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '2')
        timeout(1)
    }

    stages {
        stage('Run Python Script') {
            steps {
                bat 'python3 view_machine_data.py'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
