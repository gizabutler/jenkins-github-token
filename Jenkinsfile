@Library('jenkins-pipelines')_
pipeline {
  agent any
  stages {
    stage('test groovy script') {
      steps {
        container('centos:7') {
        sh 'echo testing script'
        wrap([$class: 'BuildUser']) {
          script {
              def userId = env.BUILD_USER_ID //"${BUILD_USER_ID}"
              def code = load("github_token.groovy")
              def token = code.github_token(userId)
              env.userId = userId
              env.token = token
            }
          sh '''
              set +x
              curl -u ${userId}:${token} https://api.github.com/user
              set -x
          '''
          }
        }
      }
    }
  }
}
