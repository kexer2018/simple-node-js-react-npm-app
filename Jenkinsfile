pipeline {
    agent any  // 在任意可用的 Jenkins 节点运行

    tools {
        nodejs 'node-lts'  // 使用我们在 Global Tool Configuration 里配置的 Node.js 版本
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/kexer2018/simple-node-js-react-npm-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // 这里可以添加部署到服务器的脚本，例如使用 SCP、Docker 或 Kubernetes 部署
            }
        }
    }
}
