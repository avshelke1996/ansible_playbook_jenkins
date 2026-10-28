pipeline{
    agent{
        label{
            label 'built-in'
        }
    }
    stages{
        stage('clean'){
            steps{
                echo "clean"
                sh 'chmod 777 usingcompose.yaml'
            }
        }
        stage('build'){
            steps{
                sh '''
            whoami
            echo "HOME=$HOME"
            ls -la ~/.ssh/ || true
            ansible-playbook usingcompose.yaml
        '''
                sh 'ansible-playbook usingcompose.yaml'
            }
        }
        stage('test'){
            steps{
                echo "test"
            } 
        }
        stage('deploy'){
            steps{
                echo "deploy"
            }
        }
    }
}
