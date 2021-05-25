node {
    stage('Code Checkout') {
        //git 'https://github.com/yuvi1695/devops-training-repo.git'
        checkout scm
    }
    
    stage('Build and Test') {
        echo 'Building Application'
        sh 'mvn clean package'
        
    }
    
    stage ('Deployment') {
        echo 'Deploying Application'
        
        deploy adapters: [tomcat9(credentialsId: 'tomcat_adminID', path: '', url: 'http://34.126.106.32:8080')], contextPath: 'index_$BUILD_NUMBER', war: '**/*.war'
    
        
    }
    
}
