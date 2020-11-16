pipeline
{
  agent {label 'node-raspberrypi3'}
  options
  {
    timestamps()
  }
  stage('checkout from scm')
  {
    steps
    {
       checkout scm
       sh 'ls -al'
    }
  }
  post
  {
   failure
   {
      emailext attachLog: true, body: "Please check ${env.BUILD_URL}', recipientProviders:[requestor()], subject: 'Failed : ${currentBuild.fullDisplayName}'
   }
  }
}
