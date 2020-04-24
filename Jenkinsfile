pipeline {
     agent any
     stages {
         stage('Upload to AWS') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
                 withAWS(region:'us-east-1',credentials:'aws-static') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'the-bucket-for-static-jenkins-pipeline')
                  }
             }
         }
	}	 
}