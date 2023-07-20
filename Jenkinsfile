@Library('my-shared-library') _

pipeline{

    agent any

    
    stages{
         
        stage('Git Checkout'){
                   when { expression {  params.action == 'create' } }
                    
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/manjumulky/java-app.git"
            )
            }
        }
        stage('Unit Test maven'){
        when { expression {  params.action == 'create' } }
                    
            steps{
               script{
                   mvnTest()
               }
            
            }
        }
        stage('Integration Test maven'){
        when { expression {  params.action == 'create' } }
         
            steps{
               script{
                   
                   mvnintegrationTest()
               }
            }
        }
        stage('Static code analysis: Sonarqube'){
         when { expression {  params.action == 'create' } }
            steps{
               script{  
                   
                   def SonarQubecredentialsId = 'sonar-j'
                   statiCodeAnalysis(SonarQubecredentialsId)
               }
            }
        }
        
        
    }   
    
} 
        