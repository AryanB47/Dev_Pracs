pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                bat 'npm install -g http-server'
                timeout(time: 60, unit: 'SECONDS') {
                    bat 'Start-Process http-server.exe'
                }
            }
        }
        
        stage('Stop') {
            steps {
                bat 'Stop-Process -Id (Get-NetTCPConnection -LocalPort 8080).OwningProcess -Force'
            }
        }
    }
}

