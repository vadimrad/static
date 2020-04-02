pipeline {
	agent any
	stages {
		stage('Linter') {
			steps {
				sh 'tidy -q -e *.html'
			}	
		}
		
		stage('Upload to AWS') {
			steps {
				withAWS(region:'us-east-1', credentials:'aws-static') {
                        		s3Upload(file:'index.html', bucket:'udacity-task3', path:'')
				}
			}
		}
	}
}
