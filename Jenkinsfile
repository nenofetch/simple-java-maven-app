node() {
    docker.image('maven:3.8.4-openjdk-11-slim').inside {
            git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'
            options {
                skipStagesAfterUnstable()
            }
            stage('Build') {
                git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'
                sh 'make'
            }
            stage('Test') {
                git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'
                sh 'make check'
                junit 'reports/**/*.xml'
            }
            stage('Deploy') {
                git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'
                sh 'make publish'
            }
        }
    }
}