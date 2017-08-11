pipeline {
  agent any
  stages {
    stage('initialiseWorkspace') {
      steps {
        parallel(
          "initialisePEWorkspace": {
            sh 'echo "script doing workspace initialisation tasks...."'
            
          },
          "initOpScriptWorkspace": {
            git(url: 'https://github.com/thoiong/my-acdsl-demo.git', credentialsId: 'becd7b32ed23b97ee61aee9f968667b0e7c33f5a')
            
          }
        )
      }
    }
    stage('buildPrep') {
      steps {
        sh 'echo "get projects directory structure ready to build ...."'
      }
    }
    stage('buildPE') {
      steps {
        sh 'echo "build bars and mmodels ...."'
      }
    }
    stage('createRCPackage') {
      steps {
        sh 'echo "create potential release candidate package ...."'
      }
    }
    stage('deploy') {
      steps {
        sh 'echo "deploy created package...."'
      }
    }
    stage('runCITest') {
      steps {
        sh 'echo "run automatic test...."'
      }
    }
    stage('archiveForNextStageTesting') {
      steps {
        archiveArtifacts '*.tar.gz'
      }
    }
  }
}