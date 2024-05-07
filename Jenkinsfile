pipeline {
    agent {
        label 'master || built-in'
    }
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building...'
                    // Simulating build success
                    currentBuild.result = 'SUCCESS'
                }
            }
        }
        stage('Test') { 
            steps {
                script {
                    echo 'Testing...'
                    // Simulating test success
                    currentBuild.result = 'SUCCESS'
                }
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
        stage('Sonar-Report') {
            steps {
                script {
                    echo 'Running SonarQube analysis...'
                    // Simulating SonarQube analysis success
                    currentBuild.result = 'SUCCESS'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying...'
                    // Simulating deployment success
                    currentBuild.result = 'SUCCESS'
                }
            }
        }
    }
}
