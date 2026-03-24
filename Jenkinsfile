pipeline {
 agent {
 node {
 label 'nodejs'
 }
} 
  parameters {
 booleanParam(name: "RUN_FRONTEND_TESTS", defaultValue: true)
 }
//stages 
 stages {
  stage('Run test') {
     parallel {
        
         stage('Backend Tests') {
		 steps {
		 sh 'node ./backend/test.js'
		 }
		 }
	 stage('Frontend Tests') {
		when { expression { params.RUN_FRONTEND_TESTS } }

		 steps {
		 sh 'node ./frontend/test.js'
		 }
		 }
            }//parallel
 } //stage

        stage('Deploy') {
 when {
 expression { env.GIT_BRANCH == 'origin/main' }
  beforeInput true
 }
 input {
 message 'Deploy the application?'
 }
 steps {
 echo 'Deploying...'
 }
 }

}//stages
//added line
}//pipline
