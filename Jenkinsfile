pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                git 'https://github.com/Kamilbeb/restassureddemo.git'
            }
        }
        stage('Run API tests') {
            steps {
                powershell 'mvn clean test'
            }
        }
        stage('Publish report') {
            steps {
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/surefire-reports', reportFiles: 'emailable-report.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }
}

