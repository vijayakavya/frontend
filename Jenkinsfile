pipeline {
  agent { label 'workstation'}

  stages {


    stage('Code Quality'){
    when {
        expression { env.TAG_NAME !=~ ".*" }
    }
          steps {
            sh 'sonar-scanner -Dsonar.host.url=http://18.206.196.93:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
          }
        }


    stage('Release'){
      when {
         expression { env.TAG_NAME ==~ ".*" }
         }
          steps {
             sh 'env'
             echo 'CI'
          }
        }

  }

}