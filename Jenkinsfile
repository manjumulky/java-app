

pipeline{

    agent any

   

    stages{
         
        stage('Git Checkout'){
                    when { expression {  params.action == 'create' } }
            steps{
            gitCheckout(
                git branch: 'main', url: 'https://github.com/manjumulky/java-app.git'
            )
            }
        } 
    }    
        
}
      
          

