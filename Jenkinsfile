pipeline{
   agent{
      node{
        label 'nodejs'
      }
   }
   parameters{
      booleanParam(name: 'RUN_FRONTEND_TEST', defaultValue: true)
   }
   stages{
     stage('Run Tests'){
       parallel {
       stage('Backend Tests'){
           steps{
              sh 'node ./backend/test.js'
           }
       }
       stage('Frontend Tests'){
          when{ expression { params.RUN_FRONTEND_TEST } }
          steps{
             sh 'node ./frontend/test.js'
               }
       }
   }
 }
}
}
