# J-p

Trigger build remotely :
pipeline sscript :
      pipeline {
    agent any

    stages {
        stage('Author name') {
            steps {
                echo 'This job is done by ${params.whoami}'
            }
        }
        stage('Creating File'){
            steps{
                echo 'filename : ${params.filename}'
                echo 'creating...'
                bat "echo 'Hello geeks' > ${params.filename}"
                echo 'sueceess'
            }
        }
    }
}
