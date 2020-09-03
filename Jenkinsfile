pipeline{

    agent {
    docker {
      image 'schoolofdevops/carts-maven'
    }

  }
   

    stages{
        stage('build'){
            steps{
                echo 'this is the build  job'
                sh '/usr/local/bin/npm install'
            }
        }
        stage('test'){
            steps{
                echo 'this is the test  job'
                sh '/usr/local/bin/npm test'
            }
        }
        stage('package'){
            steps{
                echo 'this is the package job'
                sh '/usr/local/bin/npm run package'
            }
        }
    }
    
    post{
        always{
            echo 'this pipeline has completed...'
        }
        
    }
    
}
