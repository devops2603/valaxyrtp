def imageName = 'valaxyrtp.jfrog.io/valaxy-docker/valaxy-rtp'
def registry  = 'https://valaxyrtp.jfrog.io'
def version   = '1.0.2'
def app
pipeline {
    agent {
       node {
         label "worker"
      }
    }
    stages {
        stage('Build') {
            steps {
                echo '<--------------- Building --------------->'
                sh 'printenv'
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo '<------------- Build completed --------------->'
            }
        }

        stage('Unit Test') {
            steps {
                echo '<--------------- Unit Testing started  --------------->'
                sh 'mvn surefire-report:report'
                echo '<------------- Unit Testing stopped  --------------->'
            }
        }
    }
}
