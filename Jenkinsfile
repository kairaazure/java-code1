node{
  stage('SCM Checkout') {
    git 'https://github.com/monbostest/java-code1.git'
    }
 def mvn_version = 'M3'
 withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
  //sh "mvn clean package"
}
  stage('compile code') {
    sh 'mvn package'
    }
  stage('docker buid'){
   sh 'docker build -t kairaazure/myapp.$BUILD_NUMBER .'
  }
  stage('push'){
   sh 'docker login -u kairaazure -p Rpa@2019@2019'
   sh 'docker push kairaazure/myapp.$BUILD_NUMBER'
  }
  stage('Deploy an Application to docker'){
   sh 'docker run -d -p 8080:8080 kairaazure/myapp.$BUILD_NUMBER '
  } 
}
