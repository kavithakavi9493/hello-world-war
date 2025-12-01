pipeline {
    //agent { label 'java' }
    agent none
    parameters([choice( choices: ['package', 'compile', 'install'], name: 'cmd1'),
        string(defaultValue: '', name: 'cmd2', trim: true)])
    stages{
        stage('hello-world-war') {
            parallel{
                stage('checkout'){
                    agent{label 'java'}
            steps {
                sh "rm -rf hello-world-war"
                sh "git clone https://github.com/kavithakavi9493/hello-world-war"
}
}
        stage('build') {
            agent{label 'java'}
            steps {
                sh "mvn clean package"
            }
        }
        
        stage('deploy') {
            agent{label 'java'}
            steps {
                sh "sudo cp /home/slave1/workspace/Hello_world_war_pipeline/target/hello-world-war-1.0.0.war /opt/apache-tomcat-11.0.14/webapps"

            }
            
            }
        }
    }
    }
}

