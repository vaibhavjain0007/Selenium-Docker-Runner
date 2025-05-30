pipeline {
    agent any
    stages {
        stage ('Pull Latest Image') {
            steps {
                bat "docker pull vaibhavj007/selenium-docker"
            }
        }
        stage ('Start Grid') {
            steps {
                bat 'docker-compose -f "C:/Users/Vaibhav Jain/OrangeHRM/Selenium-Docker-Runner/docker-compose.yml" up -d hub chrome firefox'
            }
        }
        stage ('Run Test') {
            steps {
                //sh
                bat 'docker-compose -f "C:/Users/Vaibhav Jain/OrangeHRM/Selenium-Docker-Runner/docker-compose.yml" up -d search-module'
            }
        }
    }

    post {
        always {
          echo "Post Run always"
          archiveArtifacts artifacts: 'output/**'
          bat 'docker-compose -f "C:/Users/Vaibhav Jain/OrangeHRM/Selenium-Docker-Runner/docker-compose.yml" down'
        }
    }
}
