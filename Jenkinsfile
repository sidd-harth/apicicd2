pipeline {
  agent any
    tools {
        maven 'M2'
        jdk 'JDK'
        nodejs 'NODEJS'
    }
    stages {
        stage ('pwd1') {
            steps {
                bat "pwd"
            }
        }
stage ('pwd2') {
            steps {
              script {
     try {
             // bat "cd hr-api/test-dir && npm install"
      
               bat "cd hr-api/test-dir/test/features && cucumber-js --format json:reports.json prod_tests.feature"
     }catch (e) {
   //if tests fail, I have used an shell script which has 3 APIs to undeploy, delete current revision & deploy previous revision
   //bat "$WORKSPACE/undeploy.sh"
       echo "Catch Block--eeee-e-e-e"
   throw e
  } finally {
   // generate cucumber reports in both Test Pass/Fail scenario
   // to generate reports, cucumber plugin searches for an *.json file in Workspace by default
   bat "cd hr-api/test-dir/test/features && cp reports.json $WORKSPACE/hr-api"

  }
              }
              }
        }
       
    }
        
     post {
    always {
      echo "I will always execute this!"
      // Cucumber report plugin
                      cucumber fileIncludePattern: '$WORKSPACE/reports.json'
    }
  }
}
