pipeline {
    agent any
    parameters {
        string (
             defaultValue:'*',
            description:'',
            name:'BRANCH_PATTERN')
       booleanParam (
            defaultValue: false,
            description:'',
            name : 'FORCE_FULL_BUILD')
            }
    stages {
        stage('Prepare') {
                steps {
                    echo 'Preparing..'
                    checkout([$class:'GitSCM',
                        branches:[[name: "origin/${BRANCH_PATTERN}"]],
                         doGenerateSubmoduleConfigurations: false,
                          extensions: [[$class: 'LocalBranch']],
                           submoduleCfg: [],
                           userRemoteConfigs: [[
                            credentialsId: '379fa736-9c39-4a16-86aa-71642aa941ca',
                              url: 'https://github.com/sksmart212/KPS']]])

    	            }
            }

         stage('Build')  {

                steps {
                    echo 'Building..'
                    build job: 'DevProject'
                      }
            }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
