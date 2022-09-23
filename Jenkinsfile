// Jenkinsfile
pipeline{
     agent any
     environment {
            DOCKERHUB_CREDENTIALS=credentials('001') // ID Identifiants globaux créer dans Jenkins
      }
      stages {
            stage('git clone') {
                 steps {
                      git branch: 'main', url: 'https://github.com/cifre0/jenkins/'
                    }
                 }
             stage('login') {
                      steps {
                         sh 'echo $DOCKERHUB_CREDENTIALS_PSW  | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                    }
                 }
//             stage('pull') {
//                  steps {
//                       sh 'docker pull ahmedchaib93/httpd:latest'
//                     }
//                   }
                }
     
            post {
                always {
                      sh 'docker logout'
                   }
                 }
}
