node('built-in') 
{
    stage('ContinousDownload')
    {
         git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ContinousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinousDeployment')
    {
        deploy adapters: [tomcat9(credentialsId: '715d4b0c-a072-4b12-b4be-39a459688e4d', path: '', url: 'http://54.167.215.114:8080')], contextPath: 'TestingPPPPPP', war: '**/*.war'
    }
    stage('Continoustesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline1/testing.jar'
    }
    stage('ContinousDelivery')
    {
        deploy adapters: [tomcat9(credentialsId: 'b0004e0c-730f-44df-8da9-aaed37f6af99', path: '', url: 'http://34.228.238.4:8080')], contextPath: 'ProdApppppppp', war: '**/*.war'
    }
}
