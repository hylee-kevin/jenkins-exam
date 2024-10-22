pipeline {
    agent any

    triggers {
        // GitHub에서 Push 이벤트가 발생할 때 빌드 트리거
        pollSCM('H/5 * * * *') // 5분마다 SCM을 폴링
    }

    stages {
        stage('Checkout') {
            steps {
                // 코드 리포지토리 체크아웃
                git url: 'https://github.com/hylee-kevin/jenkins-exam.git', branch: 'main'
            }
        }

        stage('Validate HTML') {
            steps {
                // HTML 파일을 검증하는 단계
                script {
                    // HTMLLint 검증 도구를 사용.
                    sh 'htmlhint index.html'
                }
            }
        }

        stage('Build') {
            steps {
                // 빌드 단계 (필요시 추가())
                echo 'Building the project...'
                // 필요한 빌드 명령어 추가
            }
        }

        stage('Deploy') {
            steps {
                // 배포 단계
                echo 'Deploying the application...'
                // 실제 배포 명령어 추가 (예: FTP 전송, AWS S3 업로드 등)
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs.'
        }
    }
}
