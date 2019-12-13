node{
  stage('SCM Checkout') {
    git 'https://github.com/kairaazure/java-code1.git'
    }
  stage('compile code') {
    sh 'mvn package'
    }
  stage('docker buid'){
   sh 'docker build -t kairaazure/myapp:$BUILD_NUMBER .'
  }
  stage('push'){
   sh 'docker login -u kairaazure -p Rpa@2019@2019'
   sh 'docker push kairaazure/myapp:$BUILD_NUMBER'
  }
  stage('Deploy an Application to docker'){
   sh 'docker run -d -P kairaazure/myapp:$BUILD_NUMBER '
  } 
}
