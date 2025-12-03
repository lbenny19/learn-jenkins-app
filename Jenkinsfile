pipeline {
    agent any
    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Artifactory Upload') {
            steps {
                script {
                    CHash = sh(
                    script: "git rev-parse --short=8 HEAD",
                    returnStdout: true).trim()
                }

                sh """
                    curl -u lbenny:Purvapalm1804@ -T log.txt "https://luxproject.luxoft.com/artifactory/hgnsd-git_lfs/${CHash}/log.txt"
                """
            }
        }
    }
}
