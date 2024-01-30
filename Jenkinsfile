pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
         stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'de6f2c82-848e-46e1-be81-98ff6e68442c', path: '',
                url: 'http://ec2-13-235-17-79.ap-south-1.compute.amazonaws.com:8080/')],
                contextPath: 'myjavaapp', war: '**/java-web-project.war'
            }
        }
    }
}
