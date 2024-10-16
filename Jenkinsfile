pipeline{
    agent any
    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
                
            }
        }
        stage('upload artifacts to jfrog'){
            steps{
                sh'curl -uadmin:AP2M4cAV2LdZbQyLZfXHmJZLYBm -T \
                ansible-${BUILD_ID}.zip \
                "http://3.93.148.217:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }
} 