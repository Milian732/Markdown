pipeline {
  agent any
  stages {
    stage('primer estado') {
      steps {
        sh 'cat /etc/passwd'
        sh 'echo "ejecutado correctamente"'
      }
    }

    stage('copiar ficheros') {
      parallel {
        stage('copiar ficheros') {
          steps {
            sh 'echo "copiando ficheros"'
          }
        }

        stage('') {
          steps {
            sh 'sleep 15'
          }
        }

      }
    }

    stage('notificacion') {
      steps {
        sh 'curl -X POST -H "Content-Type: application/json" -d "{\\"chat_id\\": \\"6400577385\\", \\"text\\": \\"Falló la tarea $JOB_NAME!! $BUILD_NUMBER,  \\", \\"disable_notification\\": false}" https://api.telegram.org/6971444615:AAHSR3v68P6lesjeZajdw-EM7tPCRnHJyxA/sendMessage'
      }
    }

  }
}