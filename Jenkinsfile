node() {
    docker.image('maven:3.8.1-adoptopenjdk-11').inside {
        git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app'
        
        stage('Build') {
            sh 'mvn -B -DskipTests clean package'
        }
        
        stage('Test') {
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
            input message: 'Lanjut tahap deploy? (klik "Procced" untuk lanjut ke tahap Deploy)'
        }

        stage('Delliver') {
            sh './jenkins/scripts/deliver.sh'
            input message: 'Sudah selesai? (klik "Procced" untuk memberhentikan)'
        }    
    }
}


