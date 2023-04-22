pipeline {
    agent { label "agentA" }
    
    triggers {
        pollSCM('* * * * *')
    }    

    stages {
        stage('clone_project_A') {
            steps {
                echo 'clone project A'
                git 'https://github.com/vincloud2/Helloworld-latest.git'
            }
        }
        stage('build_project_A') {
            steps {
                echo 'build_projectA'
                sh 'yum install maven -y'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
        } 
        stage('Deploy_project_A') {
            steps {
                echo 'Deploy_project_A'
                deploy adapters: [tomcat8(credentialsId: 'tomcat_admin', path: '', url: 'http://54.254.142.74:8080/')], contextPath: null, war: '**/*.war'
            }
        }
        stage('Deploy_Test_team') {
            steps {
                echo 'Deploy_project_A'
            }
        } 
        stage('Deploy_production_1') {
            steps {
                echo 'Deploy_production_1'
            }
        } 
        stage('Deploy_production_2') {
            steps {
                echo 'Deploy_production_2'
            }
        }        
    }
}
