node() {
    docker.image('maven:3.8.1-adoptopenjdk-11').inside {
        git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'

        stage('Build') {
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


