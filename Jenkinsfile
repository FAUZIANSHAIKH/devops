@Library('jenkins-shared-library') _

pipeline{
    agent any
    stages{
        stage('Sonar Analysis'){
            steps{
                sonar("Sonar")
            }
        }
        stage('Nexus Publish'){
            steps{
                nexuspublish("Nexus Publish")
            }
        }
        stage('Build'){
            steps{
                build("Build")
            }
        }
        stage('Image Push'){
            steps{
                imagepush("Image Push")
            }
        }
        stage('BDD'){
            steps{
                bdd("BDD")
            }
        }
        stage('Parallel Stages'){
              parallel{
                stage('Nexus Publish'){
                    steps{
                        echo "Running as a Parrallel Stage"
                        nexuspublish("Nexus Publish")
                    }
                }
                stage('BDD'){
                    steps{
                        echo "Running as a Parrallel Stage"
                        bdd("BDD")
                    }
                }
              }
        }
              
    }
}
