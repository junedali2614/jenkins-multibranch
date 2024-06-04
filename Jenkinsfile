pipeline {
 agent none
 stages {
   stage('Upstream pipeline') {
    steps {
     script {
       node() {
         checkout scm
         build job: 'pipeline-code-test', propagate: true,
         parameters: [
		      [$class: 'StringParameterValue', name: 'MESSAGE', value: "Juned"]
		 ]
       }
     }
   }
 }
}
}