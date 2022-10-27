pipeline {
    agent any

    stages {
        stage('building maven package') {
            steps {
               sh 'mvn clean install'
            }
        }
        stage('copyting into tomcat server') {
            steps {
              sh '''scp $WORKSPACE/target/*.war ansadmin@172.31.26.161:~
                    ssh ansadmin@172.31.26.161 "sudo cp /home/ansadmin/*.war /var/lib/tomcat9/webapps/"
                 '''
            }
        }
    }
}
