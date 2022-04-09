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
                
               sh 'pwd'
            }
        }
         stage('push') {
            steps {
             // withCredentials([file(credentialsId: 'dockerpass', variable: 'dockerpass')]) {
    // some block
}
                sh 'docker ps'
            }
        }
         stage ('Docker build') {
             steps {
                 sh 'docker build -t tawfiq15/tomcatweb . '
                 sh 'docker push tawfiq15/tomcatweb '
             }
       
         }
    }  
    

post {
        always {
            echo "Always display this message "
        }
        failure {
            echo "Job failed ...."
        }
        success {
            echo "Successful run "
        }
        unstable {
            echo "The job is unstable "
        }
} 

