pipeline {
  agent {
    docker {
                  image 'maven:3-alpine'
                  args '-v /root/.m2:/root/.m2'
           }
       }
  stages {
    stage('build') {
        steps {
          sh 'mvn clean package'
             }
         }
   stage('test') {
       steps{
         sh 'mvn test'
            }
       post{
         always {
               junit 'target/surefire-reports/*.xml'
                }
            }
        }
   stage('build') {
      steps{
        sh 'mvn install package'
         }
      }
  }
}
             
 
    
