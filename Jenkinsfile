pipeline {
    agent any

    triggers {
        githubPush()   // 🚀 triggers on GitHub webhook
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Cloning repo with credentials..."
                git branch: 'main',
                    url: 'https://github.com/Pandu-18/jenkins-script.git',
                    credentialsId: 'github-cred'
            }
        }

        stage('Build') {
            steps {
                echo "Simulating build..."
                sh 'ls -l'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                echo "Deploying WAR file to Tomcat..."
                sh '''
                    cp hello.war /home/ubuntu/tomcat9/webapps/
                    ls -l /home/ubuntu/tomcat9/webapps/
                '''
            }
        }

        stage('Restart Tomcat') {
            steps {
                echo "Restarting Tomcat..."
                sh '''
                    /home/ubuntu/tomcat9/bin/shutdown.sh || true
                    sleep 5
                    /home/ubuntu/tomcat9/bin/startup.sh
                '''
            }
        }
    }
}
