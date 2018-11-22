node('master') {
   stage('Checkout')
    {
        checkout scm
    }
    stage('Clean')
    {
        bat 'mvn clean'
    }
    stage('Test')
    {
      bat 'mvn test'
    }
   
   
    stage('Packaging')
    {
        bat 'mvn install'
    }
   stage('Deploy?')
    {
       input 'Proceed to Deploy?'
    }
   stage('Deploy')
   {
      bat 'mvn package -Ddeploy.to.weblogic -Ddeploy.for.weblogic'
   }
    /*stage('Deploy')
    {
        
     parallel firstBranch: {
       build job: 'New_appl', parameters: [string(name: 'DEPLOYMENT_ARTIFACT_PATH', value: 'C:\\jenkins_installpath\\workspace\\BankAppl\\target'), string(name: 'DEPLOYMENT_ARTIFACT_NAME', value: 'BankExample')]
    }, secondBranch: {
        build job: 'Tomcat_appl', parameters: [string(name: 'DEPLOYMENT_ARTIFACT_PATH', value: 'C:\\jenkins_installpath\\workspace\\BankAppl\\target'), string(name: 'DEPLOYMENT_ARTIFACT_NAME', value: 'BankExample')]
    },
    failFast: true
    
    }*/
}

    
 
