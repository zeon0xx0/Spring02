pipeline {
    agent any
    
    tools {
        maven 'my-maven'  // 젠킨스에서 설치한 이름
    }

    stages {
        stage('0. 자동화 확인1') { steps { echo '스테이지 출발' } }
        
        stage('1. Build') {
            steps {
                echo 'Maven으로 빌드 시작'
                sh 'mvn clean package'
            }
        }
        stage('2. Check Docker') {
            steps {
                sh 'docker version'
            }
        }

        stage('3. Docker Build') {
            steps {
                sh 'docker build -t ex02-app:latest .'
            }
        }
    }
}
