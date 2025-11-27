pipeline {
    agent { label 'java' }
    stages {
        stage('checkout') {
            steps {
                sh "rm -rf hello-world-war"
                sh "git clone https://github.com/kavithakavi9493/hello-world-war"
}
}
        stage('build') {
            steps {
                sh "mvn clean package"
            }
        }
        
        stage('deploy') {
            steps {
                sh "sudo cp /home/slave1/workspace/Hello_world_war_pipeline/target/hello-world-war-1.0.0.war /opt/apache-tomcat-11.0.14/webapps"

            }
            
            }
        }
    }

