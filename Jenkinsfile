pipeline {

agent any

stages {

stage ('Build using Maven') {
    steps {
        echo '*******mvn build start*******'
        echo '*******mvn build done*******'
    }
}

stage('unit testing') {
    steps {
        echo '*******unit testing starts*******'
        //junit skipPublishingChecks: true, testResults: '**/target/surefire-reports/TEST-*.xml'   
        echo '*******unit testing ends*******'
               
    }
}
/*
stage ('Test using CheckMarX') {
   
    steps {
        echo '*******CheckMarX start*******'
        
   
        echo '*******CheckMarX end*******'
    }
   
}


stage ('Upload to Jfrog') {
     steps {
         echo '*******upload to JFrog start*******'
        
       //  echo '*******upload to JFrog End*******'
 //    }
//}

// stage ('Download from Jfrog') {
//      steps {
//          echo '*******download from JFrog start*******'
//         
//          echo '*******download from JFrog End*******'
//      }
// }


        
       
 stage ('Deploy on tomcat') {
      steps {
          echo '*******deploy on tomcat Start*******'
        echo '*******deploy on tomcat done*******'
      }
  }
  
       // stage('send mail') {
       // steps {
        //    step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'bhagyakakumanu@gmail.com.com', sendToIndividuals: true])
       // }
       // }
 }
}
// comment line
