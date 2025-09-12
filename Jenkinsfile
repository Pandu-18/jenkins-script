node {
    stage('Checkout Code') {
        checkout([$class: 'GitSCM',
                  branches: [[name: '*/main']],
                  userRemoteConfigs: [[url: 'https://github.com/Pandu-18/jenkins-script.git']]
        ])
    }

    stage('Deploy to Tomcat') {
        echo "Deploying WAR to Tomcat..."
        sh '''
            cp hello.war /home/ubuntu/tomcat9/webapps/
        '''
    }
}
