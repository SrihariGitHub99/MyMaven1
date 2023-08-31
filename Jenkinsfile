pipeline
{
    agent any
    stages
    {
        stage('Continous download')
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
             deploy adapters: [tomcat9(credentialsId: '715d4b0c-a072-4b12-b4be-39a459688e4d', path: '', url: 'http://3.89.43.211:8080')], contextPath: 'Testing111', war: '**/*.war'
            }
        }
        stage('Continous Testing')
        {
            steps
            {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
            }
        }
         stage('Continous Delivery')
        {
            steps
            {
            deploy adapters: [tomcat9(credentialsId: 'b0004e0c-730f-44df-8da9-aaed37f6af99', path: '', url: 'http://54.80.217.55:8080')], contextPath: 'Prodapp111', war: '**/*.war'
            }
        }


    }
}

