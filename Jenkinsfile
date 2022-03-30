pipeline {

agent any

stages {
/*
stage('Code checkout from bitbucket'){
    steps {
        echo '*******Code checkout*******'
       // git url: "ssh://git@bitbucket.devops.idfcbank.com:7999/do/idfc-ms-gateway.git", credentialsId: '007ababd-3b90-4b00-88f6-ba46829d055d'
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
        sh 'mvn clean install'
        //-Dmaven.wagon.http.ssl.insecure=true -Drepo.id=cms-stride -Drepo.login=gBL9g2hjHb'
        echo '*******mvn build done*******'
    }
}

stage('unit testing') {
    steps {
        echo '*******unit testing starts*******'
        junit skipPublishingChecks: true, testResults: '**/target/surefire-reports/TEST-*.xml'   
        echo '*******unit testing ends*******'
               
    }
}
/*
stage ('Test using CheckMarX') {
   
    steps {
        echo '*******CheckMarX start*******'
        
    //step([$class: 'CxScanBuilder', comment: '', configAsCode: true, credentialsId: 'CheckmarxAdmin', customFields: '', excludeFolders: '', exclusionsSetting: 'job', failBuildOnNewResults: false, filterPattern: '', fullScanCycle: 10, generatePdfReport: true, groupId: '14', isProxy: false, password: '{AQAAABAAAAAQuS0flM51g0FeEL8tg0KFkzAKx67QTxAk8RG33TyUuTw=}', preset: '7', projectName: 'IDFC-MS-Gateway', sastEnabled: true, serverUrl: ' https://checkmarx.idfcbank.com', sourceEncoding: '6', useOwnServerCredentials: true, username: '', waitForResultsEnabled: true])
    
        echo '*******CheckMarX end*******'
    }
   
}


stage ('Upload to Jfrog') {
     steps {
         echo '*******upload to JFrog start*******'
        /* rtUpload (
                serverId: 'artifactory_idfcbank',
                spec:
                    '''{
                      "files": [
                        {
                          "pattern": "/data/jenkins/workspace/Digital Onboarding/DemoPipeline/target/cicd-0.0.1-SNAPSHOT.war",
                          "target": "maven-local/idfc/digital_onboarding/master/"
                        }
                     ]
                    }''',
            ) */
       //  echo '*******upload to JFrog End*******'
 //    }
//}

// stage ('Download from Jfrog') {
//      steps {
//          echo '*******download from JFrog start*******'
//          rtDownload (
//                   serverId: 'artifactory_idfcbank',
//                   spec: '''{
//                           "files": [
//                             {
//                               "pattern": "maven-local/idfc/digital_onboarding/master/",
//                               "target": "D:/"
//                             }
//                          ]
//                         }''',
//             ) 
//          echo '*******download from JFrog End*******'
//      }
// }

//         // stage ('Publish build info') {
//         //     steps {
//         //         rtPublishBuildInfo (
//         //             serverId: 'artifactory_idfcbank'
//         //         )
//         //     }
//         // }
        
       
 stage ('Deploy on tomcat') {
      steps {
          echo '*******deploy on tomcat Start*******'
        //   sshagent(['ID_WEBLOGIC_DIGITAL_ONBOARDING']) {
        //   sh "scp -v -o StrictHostKeyChecking=no /data/jenkins/workspace/Digital Onboarding/DemoPipeline/target/cicd-0.0.1-SNAPSHOT.war deployer@10.5.25.170:7001/weblogicdomain/onboardapp/servers/AdminServer/upload/sample1.war/app/"
          echo '*******deploy on tomcat done*******'
      }
  }
  
        stage('send mail') {
        steps {
            step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'bhagyakakumanu@gmail.com.com', sendToIndividuals: true])
        }
        }
 }
}
