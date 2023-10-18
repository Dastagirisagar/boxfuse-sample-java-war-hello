pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  stages {
      stage("git"){
          steps{
                git branch: 'master', url: 'https://github.com/Dastagirisagar/boxfuse-sample-java-war-hello.git'
          
          }
      }
      stage("build"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy"){
          steps{
                deploy adapters: [tomcat9(credentialsId: 'aae73344-3ada-4dce-9c9e-40cc2d7e512f', path: '', url: 'http://3.110.119.91:8080/')], contextPath: 'pipeline', war: '**/*.war'
          }
      }
  }
}
