pipeline {
  agent any
  stages {
    stage('initialiseWorkspace') {
      steps {
        parallel(
          "initialisePEWorkspace": {
            sh 'echo "script doing project workspace initialisation tasks...."'
            
          },
          "initOpScriptWorkspace": {
            sh 'echo "script doing scripts workspace initialisation tasks...."'
            
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
