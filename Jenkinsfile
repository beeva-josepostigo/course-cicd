node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: '870eb7f1-2f0a-4a75-86c2-11ff7c27541a', url: 'git@github.com:beeva-josepostigo/course-cicd.git'
  }
}

