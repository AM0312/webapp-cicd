pipeline {
    agent {
        label 'master || built-in'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
//         stage('Sonar-Report') {
//             steps {
//             sh 'mvn sonar:sonar \
//   -Dsonar.projectKey=jenkins_project \
//   -Dsonar.host.url=http://localhost:9000 \
//   -Dsonar.login=5f09ded7e5db4d0ea0dcfd937c181af706e60475'
//             }
//         }
        stage('Test') { 
            steps {
                sh 'mvn test' 
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
                    env.SONAR_TOKEN = '3cf8f8dd674e6f64a5938e7467498f4fe41621c8'
                    sh 'echo $SONAR_TOKEN'
                    sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=AM0312_webapp-cicd'
                }
            }
        }
    }
}
