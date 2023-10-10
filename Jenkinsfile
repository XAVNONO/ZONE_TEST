pipeline {
  agent any

  environment {
      IMAGE_TAG = "xavnono/python_app"
      DOCKER_HUB_USER = "xavnono"
      DOCKER_HUB_PAT = "Xavi0501!"
                }

        stages {
          stage('Analyze image') {
            steps {
                // Install Docker Scout
                sh 'curl -sSfL https://raw.githubusercontent.com/docker/scout-cli/main/install.sh | sh -s -- -b /usr/local/bin'
                
                // Log into Docker Hub
                sh 'echo $DOCKER_HUB_PAT | docker login -u $DOCKER_HUB_USER --password-stdin'

                // Analyze and fail on critical or high vulnerabilities
                sh 'docker-scout cves $IMAGE_TAG --exit-code --only-severity critical,high'
                  }
              }
          }
      }
