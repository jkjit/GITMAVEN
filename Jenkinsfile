node {
  stage('SCM Checkout') {
        git 'https://github.com/jkjit/GITMAVEN'
        }
   stage('Compile Project'){
     //Get MAVEN HOME PATH
     def mvnHome = tool name: 'maven-3', type: 'maven'
     sh "${mvnHome}/bin/mvn package"
       }
  stage('Email Notification'){
  //mail bcc: '', body: '''Hi WELCOME TO JENKINS EMAIL ALERT
//Thanks JayaKumar''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'jkck99@gmail.com'
    echo 'Successfully sent email newone'
  }  
 // stage('Slack Notification') {
    //slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'jenkins-pipeline-demo', color: 'good', message: 'welcome to Jenkins slack!', teamDomain: 'RDDEVOPS', tokenCredentialId: 'slack-demo'
    
  //}
}
