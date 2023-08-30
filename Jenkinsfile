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
             deploy adapters: [tomcat9(credentialsId: '715d4b0c-a072-4b12-b4be-39a459688e4d', path: '', url: 'http://50.19.16.205:8080')], contextPath: 'Testingg', war: '**/*.war'
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
            deploy adapters: [tomcat9(credentialsId: 'b0004e0c-730f-44df-8da9-aaed37f6af99', path: '', url: 'http://54.88.0.51:8080')], contextPath: 'Prodapppp', war: '**/*.war'
            }
        }
        
        
    }
}

