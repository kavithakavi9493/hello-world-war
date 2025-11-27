pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'https://github.com/kavithakavi9493/hello-world-war'
}
}
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('deploy') {
            steps {
                sh 'sudo cp /var/lib/jenkins/workspace/Helloworld_war_job/target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.49/webapps/helloworld1'

            }
            
            }
        }
    }

