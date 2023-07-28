

pipeline{

    agent any
    
    
    stages{
         
        stage('Git Checkout'){
                   
                    
            steps{
                script{
                   GitCheckout(
                       branch: "main",
                       url: "https://github.com/manjumulky/java-app.git"
                   )
                }




            }

        }
        
    }  
    
} 
        