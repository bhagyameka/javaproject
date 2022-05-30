pipeline {

agent any

stages {
/*
stage('Code checkout from bitbucket'){
    steps {
        echo '*******Code checkout*******'
      
        echo '*******Code checkout done*******'

        echo '*******mvn version start*******'
        sh 'mvn --version'
        echo '*******mvn version end*******'
     
    }
}
*/
stage ('Build using Maven') {
    steps {
        echo '*******mvn build start*******'
       
        echo '*******mvn build done*******'
    }
}

stage('unit testing') {
    steps {
        echo '*******unit testing starts*******'
        
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
       
       // }
       // }
 }
}
// comment line
