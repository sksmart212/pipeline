pipeline {
    agent any
    parameters {
        string (
             defaultValue:'*',
            description:'',
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
                        branches:[[name: "origin/master"]],
                         doGenerateSubmoduleConfigurations: false,
                          extensions: [[$class: 'LocalBranch']],
                           submoduleCfg: [],
                           userRemoteConfigs: [[
                            credentialsId: '379fa736-9c39-4a16-86aa-71642aa941ca',
                              url: 'https://github.com/sksmart212/KPS']]])

    	            }
            }

        stage('Build') {
            steps {
                echo 'Building..'
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
