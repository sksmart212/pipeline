pipeline{
    agent any
   stages   {
        stage('Complie stage'){

        steps {
            withMaven(maven : 'mavens'){
            sh 'mvn clean compile'
        }
        }
        }
        stage ('Testing Stage'){
         steps {
                    withMaven(maven : 'mavens'){
                    sh 'mvn test'
                }
                }
        }

         stage ('Deploy Stage'){
                 steps {
                            withMaven(maven : 'mavens'){
                            sh 'mvn deploy'
                        }
                        }
                }
   }
}
