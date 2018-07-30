


pipeline {
	agent any

		tools {
			jdk "Java-1.8"
			maven "Maven-3.5.3"
		}

		parameters {
			choice(
				name: 'branches',
				choices:"master\nbranch1\nbranch2",
				description: 'Select the branch to checkout from')
		}

	stages {
	     stage('SCM checkout') {
		steps{
			echo "pulling changes from the branch ${params.branches}"
			git url: 'https://github.com/Anusha-DevOp/HelloWorld.git', branch : "${params.branches}"
		}
	      }

	     stage('Execute Maven') {
		steps {
			bat 'mvn clean package'
		       }
              }

	     
				
}
	     