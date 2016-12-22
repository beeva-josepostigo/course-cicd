node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: '870eb7f1-2f0a-4a75-86c2-11ff7c27541a', url: 'git@github.com:beeva-josepostigo/course-cicd.git'
  }
  
  stage('Test') {
  sh './simplehttpserver/tests/unittests.sh ./simplehttpserver/'
  }

  stage('Package and publish') {
    sh "tar -zcvf simplehttpserver-${env.JO_NAME}-${env.BUILD_ID}.tar.gz ./simplehttpserver"
    sh "aws s3 cp simplehttpserver-${env.JOB_NAME}-${env.BUIL_ID}.tar.gz s3://clase-gendevops2-cicd-ci/"
  }

}

