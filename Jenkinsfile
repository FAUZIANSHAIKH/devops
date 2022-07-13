@Library('jenkins-shared-library') _

pipeline{
    agent any
    stages{
        stage('Sonar Analysis'){
            steps{
                sonar("Sonar")
            }
        },
        stage('Nexus Publish'){
            steps{
                nexus-publish("Nexus Publish")
            }
        },
        stage('Build'){
            steps{
                build("Build")
            }
        },
        stage('Image Push'){
            steps{
                image-push("Image Push")
            }
        },
        stage('BDD'){
            steps{
                bdd("BDD")
            }
        }
    }
}