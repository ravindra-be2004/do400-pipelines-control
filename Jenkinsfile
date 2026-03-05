node('nodejs') {
  stage('Checkout') {
  git branch: 'main',
      url: 'https://github.com/ravindra-be2004/Do400-pipelines-control'
  }
  stage('Backend Tests'){
   sh 'node ./backend/test.js'
  }
  stage('Frintend Tests'){
  sh 'node ./frontend/test.js'
  }
}

