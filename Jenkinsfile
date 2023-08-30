pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
         stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '6c6df49f-cace-4300-96c6-52ea4c185853', path: '',
                url: 'http://ec2-65-2-169-133.ap-south-1.compute.amazonaws.com:8080/')],
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
