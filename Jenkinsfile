@Library('my-shared-library') _

pipeline{

    agent any

    
    stages{
         
        stage('Git Checkout'){
                    
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/manjumulky/java-app.git"
            )
            }
        }
        stage('Unit Test maven'){
                    
            steps{
               script{
                   mvnTest()
               }
            
            }
        }
        
        stage('Static code analysis:Sonarqube'){
                    
            steps{
               script{
                   statiCodeAnalysis()
               }
            
            }
        }
    }   
    
}         