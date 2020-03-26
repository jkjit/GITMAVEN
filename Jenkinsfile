node {
  stage('SCM Checkout') {
        git 'https://github.com/jkjit/GITMAVEN'
        }
   stage('Compile Project'){
     //Get MAVEN HOME PATH
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
       }
  stage('Sonarqube Analysis'){
     def mvnHome = tool name: 'maven-3', type: 'maven'
    sh "${mvnHome}/bin/mvn sonar:sonar \
   -Dsonar.projectKey=newsonar \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=bbf95eb29f2ad25cbf7ff8cc3edb4db68ed3eca4
  }
  stage('Email Notification'){
//  mail bcc: '', body: '''Hi WELCOME TO JENKINS EMAIL ALERT
//Thanks JayaKumar''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'jkck99@gmail.com'
    echo 'Successfully sent dummy email JK'
  }  
 // stage('Slack Notification') {
    //slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'jenkins-pipeline-demo', color: 'good', message: 'welcome to Jenkins slack!', teamDomain: 'RDDEVOPS', tokenCredentialId: 'slack-demo'
    
  //}
}
