pipeline {
  agent none
  stages {
    stage('build') {
      agent {
        docker {
          image 'schoolofdevops/node:4-alpine'
        }

      }
      steps {
        echo 'this is the build job'
        sh 'npm install'
      }
    }

    stage('test') {
      agent {
        docker {
          image 'schoolofdevops/node:4-alpine'
        }

      }
      steps {
        echo 'this is the test job'
        sh '''npm install
npm test'''
      }
    }

    stage('package') {
      agent {
        docker {
          image 'schoolofdevops/node:4-alpine'
        }

      }
      steps {
        sh '''npm install
npm run package'''
        archiveArtifacts '**/distribution/*.zip'
      }
    }
   
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}
