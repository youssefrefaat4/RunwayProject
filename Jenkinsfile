def DEPLOY_ENVIRONMENT="dev"

pipeline {

       agent any
      
    stages {
        
        stage('Prepare-and-deploy') {
            when {branch 'main'}
            steps {
                    sh 'echo ######################Exporting  DEPLOY_ENVIRONMENT ######'
                    echo DEPLOY_ENVIRONMENT
                    sh """
                    export DEPLOY_ENVIRONMENT=${DEPLOY_ENVIRONMENT}
                    printenv | grep -i DEPLOY_ENVIRONMENT
                    chmod +x runway
                    runway deploy --ci
                   """
                }
        }
    }
}