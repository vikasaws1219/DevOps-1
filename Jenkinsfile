@Library('my_jenkins_library') _
pipeline{
    
    agent any

    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose Create/Destroy')
    }

    stages{

        stage('Git Checkout'){

            when { expression { params.action == 'create' } }

            steps{

                script{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/vikasaws1219/DevOps-1.git"

                    )
                    
                }
            }
        }
        stage('Mvn Clean Pckage'){

            when { expression { params.action == 'create' } }

            steps{

                script{
                    mvnCleanPackage()                    
                }
            }
        }
        
        stage('Unit Test Maven'){

            when { expression { params.action == 'create' } }

            steps{

                script{

                    mvnTest()

                }
            }
        }
        stage('Integration Test Maven'){

            when { expression { params.action == 'create' } }

            steps{

                script{

                    mvnIntegrationTest()

                }
            }
        }
        stage('Static Code Analysis: Sonarqube'){

            when { expression { params.action == 'create' } }

            steps{

                script{
                    
                    def SonarQubecredentialsId = 'sonar-api'
                    staticCodeAnalysis(SonarQubecredentialsId)

                }
            }
        }
    }

}
