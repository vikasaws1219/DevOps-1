@Library('my-jenkins-library') _
pipeline{
    
    agent any

    paramaters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose Create/Destroy')
    }

    stages{

        stage('Git Checkout'){

            when { expression { param.action== 'create' } }

            steps{

                script{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/vikasaws1219/DevOps-1.git"

                    )
                    
                }
            }
        }
        stage('Unit Test Maven'){

            when { expression { param.action== 'create' } }

            steps{

                script{

                    mvnTest()

                }
            }
        }
        stage('Integration Test Maven'){

            when { expression { param.action== 'create' } }

            steps{

                script{

                    mvnIntegrationTest()

                }
            }
        }
    }

}
