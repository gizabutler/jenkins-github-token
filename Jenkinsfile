@Library('jenkins-pipelines')_
pipeline {
  agent {
     kubernetes {
    containerTemplate {
        name 'centos'
        image 'centos:7'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  stages {
    stage('test groovy script') {
      steps {
        sh 'echo testing script'
        userGithubToken()
        // wrap([$class: 'BuildUser']) {
        //   script {
        //       def userId = env.BUILD_USER_ID //"${BUILD_USER_ID}"
        //       def code = load("github_token.groovy")
        //       def token = code.github_token(userId)
        //       env.userId = userId
        //       env.token = token
        //     }
        //   sh '''
        //       set +x
        //       curl -u ${userId}:${token} https://api.github.com/user
        //       set -x
        //   '''
        //   }
        }
      }
    }
}
