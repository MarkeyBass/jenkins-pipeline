  pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Goodbye'){
            steps {
                echo 'Goodbye'
                mail bcc: '', body: 'Im inside my step', cc: '', from: '', replyTo: '', subject: 'Step message', to: 'markeybass@gmail.com'
            }
        }

    }
    post{
            success{
                mail bcc: '', body: 'This time everything is good.', cc: '', from: '', replyTo: '', subject: 'Successful build', to: 'markeybass@gmail.com'
            }
            failure{
                step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'markeybass@gmail.com', sendToIndividuals: false])
            }
    }
  }
