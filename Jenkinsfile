pipeline {
    agent any 

    tools {
        gradle 'gradle'  
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/jayakanthmn/gradlenew.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  
            }
        }

       stage('Test') {
           steps {
               sh 'gradle display'  
           }
        }

              
        stage('Run Application') {
            steps {
                
                sh 'gradle run'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
