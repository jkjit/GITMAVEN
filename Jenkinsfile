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
    sh "${mvnHome}/bin/mvn sonar:sonar \
  -Dsonar.projectKey=jk-test-2 \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=1a716a653cc4982695f9c7d2647d1d9aa7568140"
  }
  stage('Email Notification'){
  mail bcc: '', body: '''Hi WELCOME TO JENKINS EMAIL ALERT
Thanks JayaKumar''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'jkck99@gmail.com'
    echo 'Successfully sent email JK'
  }  
 // stage('Slack Notification') {
    //slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'jenkins-pipeline-demo', color: 'good', message: 'welcome to Jenkins slack!', teamDomain: 'RDDEVOPS', tokenCredentialId: 'slack-demo'
    
  //}
}
