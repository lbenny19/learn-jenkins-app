pipeline {
    agent any
    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Upload to Artifactory') {
            steps {
                sh """
                    curl -u lbenny:Purvapalm1804@ -T log.txt "https://luxproject.luxoft.com/artifactory/hgnsd-git_lfs/cmeta2"
                """
            }
        }
    }
}
