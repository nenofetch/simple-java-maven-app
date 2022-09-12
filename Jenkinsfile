node() {
    docker.image('maven:3.8.4-openjdk-11-slim').inside {
            stage('Build') {
            git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'
            options {
                skipStagesAfterUnstable()
            }
            stage('Build') {
                sh 'make'
            }
            stage('Test') {
                sh 'make check'
                junit 'reports/**/*.xml'
            }
            stage('Deploy') {
                sh 'make publish'
            }
        }
    }
}