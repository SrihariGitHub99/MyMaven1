pipeline
{
    agent any 
    stages
    {
     stage('Continous Download')
     {
      steps 
      {
        git 'https://github.com/SrihariGitHub99/MyMaven1.git'
      }
     }
      stage('Continous Build')
     {
      steps 
      {
        sh 'mvn package'
      }
     }
        stage('Continous Deployment')
     {
      steps 
      {
       deploy adapters: [tomcat9(credentialsId: '03341149-707e-4900-bda4-eb54b638a7c8', path: '', url: 'http://172.31.7.67:8080/')], contextPath: 'TestingGCVHBKJN', war: '**/*.war'
      }
     }
        stage('Continous Testing')
     {
      steps 
      {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        
        sh 'java -jar  /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'
      }
     }
        stage('Continous Delivery')
     {
      steps 
      {
       deploy adapters: [tomcat9(credentialsId: 'f0a9b169-d6e5-4b9e-ac79-b7739f38a500', path: '', url: 'http://172.31.3.55:8080/')], contextPath: 'ProdAppppp', war: '**/*.war'
      }
     }
     
    }
}
