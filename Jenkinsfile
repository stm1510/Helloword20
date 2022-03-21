pipeline {
    agent any
    tools {
       maven 'maven'
    }

    stages {
        stage('build') {
            steps {
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
                
            }
        }
         stage('test') {
            steps {
                echo 'Hello test'
                sleep 5
            }
        }
         stage('deploy') {
            steps {
                echo 'Hello deploy'
               sh 'pwd'
            }
        }
         stage('push') {
            steps {
                echo 'Hello push'
                sh 'docker ps'
            }
        }
         stage ('Docker build'){
            sh ' docker build -t tawfiq15/projject . '
        }
    }
    

post {
        always {
            echo "Always display this message "
        }
        failure {
            echo "Job failed "
        }
        success {
            echo "Successful run "
        }
        unstable {
            echo "The job is unstable "
        }
    } 
}
