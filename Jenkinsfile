


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


	     stage('check branch') {
			//when {
			//	expressioin { params.branches == 'branch2'}
			//	}
		//	steps {
		//		bat 'mvn -f D:/DevOps/maven/parameter/com.parameter.sample clean package'}
		
			steps {
				script {
				     if ("${params.branches}" == "branch1") {
					currentBuild.result = 'ABORTED'
					error('Jenkinsfile is not found in this branch')
				      }
				
				     elseif ("${params.branches}" == "branch2") {
					bat 'mvn -f D:/DevOps/maven/parameter/com.parameter.sample clean package'}
				 }
			}
		}



	   //  stage('Execute Maven') {
	//	steps {
			//bat 'mvn -f D:/DevOps/maven/parameter/com.parameter.sample //clean package'
//		       }
  //            }

	     
				
}
}	     