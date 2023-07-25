@Library('my-shared-library') _

pipeline{

    agent any
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
    }

    
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
        
        stage('Quality Gate Status check : Sonarqube'){
         when { expression {  params.action == 'create' } }
            steps{
               script{  
                   
                   def SonarQubecredentialsId = 'sonar-j'
                   qualityGateStatus(SonarQubecredentialsId)
               }
            }
        }
        
        stage('Maven Build : maven'){
         when { expression {  params.action == 'create' } }
            steps{
               script{  
                   
                   mvnBuild()
               }
            }
        }
    }  
    
} 
        