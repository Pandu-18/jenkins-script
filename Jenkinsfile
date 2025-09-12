node {
    stage('Checkout Code') {
        git branch: 'main', url: 'https://github.com/Pandu-18/jenkins-script.git'
    }

    stage('Deploy to Tomcat') {
        echo "Deploying WAR to Tomcat..."
        sh '''
            # Stop Tomcat if running
            /home/ubuntu/tomcat9/bin/shutdown.sh || true

            # Copy WAR into Tomcat webapps
            cp hello.war /home/ubuntu/tomcat9/webapps/

            # Start Tomcat
            /home/ubuntu/tomcat9/bin/startup.sh
        '''
    }
}
