pipeline {
    //agent { label 'java' }
    agent none
    //parameters([choice( choices: ['package', 'compile', 'install'], name: 'cmd1'),
      //  string(defaultValue: '', name: 'cmd2', trim: true)])
    parameters {
string(name: 'cmd', defaultValue: '', description: 'A sample string parameter')
booleanParam(name: 'SAMPLE_BOOLEAN', defaultValue: true, description: 'A boolean parameter')
choice(name: 'cmd1', choices: ['package', 'install', 'compile'], description: 'Choose one option')
}
   // withCredentials([usernamePassword(credentialsId: "f896c97f-350e-4702-a027-60886e296cab", usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                 // your command here
            
    stages{
        stage('hello-world-war') {
            parallel{
                stage('checkout'){
                    agent{label 'java'}
            steps {
                withCredentials([usernamePassword(
                            credentialsId: 'f896c97f-350e-4702-a027-60886e296cab',
                            usernameVariable: 'Kavitha_USER',
                            passwordVariable: 'Kavitha_PASS'
                     /*  withCredentials([sshUserPrivateKey(
                            credentialsId: 'ffeac448-2ed6-4ca8-9879-4be360646164',
                             keyFileVariable: 'Kavitha_SSH_KEY',
                             usernameVariable: 'Kavitha_SSH_USER' */
                        )]) {
                sh "rm -rf hello-world-war"
                sh "git clone https://github.com/kavithakavi9493/hello-world-war"
}
}
                }
        stage('build') {
            agent{label 'java'}
            steps {
                sh "mvn $cmd $cmd1"
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

