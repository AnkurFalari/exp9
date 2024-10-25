﻿pipeline {
    agent any


    stages {
        stage('Build docker image') {
            steps {
                scripts {
                    bat "docker build -t ankurmca/dock ."
                }
            }
        }
      stage('Build & run docker container') {
          steps {
                scripts {
                    bat "docker rm -f my-app-container || exit 0"
                    
                    bat "docker run -d --name my-app-container ankurmca/dock"
                }
          }
      }
    }
}