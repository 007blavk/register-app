pipeline{
  agent { label 'jenkins-agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
      stage("Cleaning up WorkSpace") {
        steps {
          cleanWs()
        }
      }
      stage("Checkout from SCM"){
        steps {
          git branch: 'main', credentialsId: 'github', url: 'https://github.com/007blavk/register-app'
        } 
      }
      stage("Build Application"){
        steps {
          sh "mvn clean package"
        }
      }
  }
}
