pipeline {
    agent {
        node {
            label 'built-in'
            customWorkspace '/data/project'
        }
    }
    stages {
        stage('clone') {
            steps {
		sh "rm -rf *"
                sh "git clone --single-branch --branch 22q1 https://github.com/vinay-aws/Assignment-1.git q1"
		sh "git clone --single-branch --branch 22q2 https://github.com/vinay-aws/Assignment-1.git q2"
            }
        }
		stage('deploy') {
            steps {
				dir ('/data/project/q2'){
					sh 'scp -i "/pemfile.pem" index.html ec2-user@172.31.39.106:/home/ec2-user/apache-tomcat-9.0.65/webapps/myapps-2'
				}
			}
		}
	}
}
