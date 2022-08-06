pipeline{
    
    agent {
        
        label 'kiwi'
    }
    
    tools{
        
        jdk 'myjava'
        maven 'mymaven'
    }
    stages{
        stage('checkout'){
            
            steps{
                
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kliakos/sparkjava-war-example.git']]])
            }
        }
        stage('package'){
            
            steps{
                sh 'mvn package'
                
                    }
        }
        stage('copy'){
            
            steps{
                
                sh 'cp -r /opt/satish/workspace/git-dev-maven/target/sparkjava-hello-world-1.0.war /opt/softwares/apache-tomcat-9.0.65/webapps/'
            }
        }
    }
}
