node() {
    docker.image('maven:3.8.1-adoptopenjdk-11').inside('-v /root/.m2:/root/.m2') {
        checkout scm
                
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


