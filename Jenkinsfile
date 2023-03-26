pipeline{
	agent any
	stages{
		stage('1-clone'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-id', url: 'https://github.com/ben-etech/team5app.git']])
			}
		}
		stage('sytemscheck'){
			steps{
				sh 'sudo systemctl status jenkins'
			}
		}
		stage('3-diskcheck'){
			steps{
				sh 'df -h'
			}
		}
		stage('4-blockcheck'){
			steps{
				sh 'lsblk'
			}
		}
        stage('5-ops-check'){
            steps{
                sh 'cat /etc/os-release'
            }
        }
        stage('6-script control'){
            steps{
              sh 'bash -x /var/lib/jenkins/workspace/team5-job-demo/script.sh'  
            }
        }
	} 
}
