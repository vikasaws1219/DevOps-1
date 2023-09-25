@Library('my-jenkins-library') _
pipeline{
    
    agent any

    stages{

        stage('Git Checkout'){

            steps{

                script{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/vikasaws1219/DevOps-1.git"

                    )
                    
                }
            }
        }

    }

}
