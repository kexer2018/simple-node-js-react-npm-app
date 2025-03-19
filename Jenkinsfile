pipeline {
    agent { 
        dockerContainer { 
            image 'node:18'  // 使用官方Node.js镜像
            remoteFs '/app'  // 可选：设置容器内工作目录
        } 
    }
    tools {
        nodejs "default"  // 确保与全局配置名称一致
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'  // 根据项目调整命令（如React需用npm run build）
            }
        }
        stage('Run') {
            steps {
                sh 'npm start'  // 启动React应用（默认监听3000端口）
            }
        }
    }
}