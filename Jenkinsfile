node() {
    docker.image('maven:3.8.1-adoptopenjdk-11').inside {
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


