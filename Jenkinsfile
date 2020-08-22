node { //single
  stage('SCM Checkout') {
    git branch: 'dev', credentialsId: 'global', url: 'https://github.com/QuangNguyenHuu/serenity-bdd-test.git'
    //git(credentialsId: 'global', url: 'https://github.com/QuangNguyenHuu/serenity-bdd-test.git', branch 'feature')
  }
  
  stage('Build project using MVN') {
    steps {
      echo 'Instruction MVN'
        //script {
          def mvnHome = tool name: 'maven-3', type: 'maven'
          def mvnCmd = "${vmnHome/bin/mvn}"
          sh "${mvnCmd} clean package"
        //}
      echo '[FINISH] Maven'
    }
  }
}

/*
//groovy script
pipeline { //multi
  agent('SCM Checkout') {
    git branch: 'dev', credentialsId: 'global', url: 'https://github.com/QuangNguyenHuu/serenity-bdd-test.git'
    //git(credentialsId: 'global', url: 'https://github.com/QuangNguyenHuu/serenity-bdd-test.git', branch 'feature')
  }
  
  stage('Build project using MVN') {
    steps {
      echo 'Instruction MVN'
        //script {
          def mvnHome = tool name: 'maven-3', type: 'maven'
          def mvnCmd = "${vmnHome/bin/mvn}"
          sh "${mvnCmd} clean package"
        //}
      echo '[FINISH] Maven'
    }
  }
  
  
  stage('Build Docker image') {
    sh 'docker build -t jacobalberty/unifi:latest'
  }
  
  stage('Push Docker image') {
    withCredentials([string(credentialsId: 'dockerPassword', variable: 'secretTest')]) {
      sh "docker login -u usr -p ${secretTest}"
    }
    sh 'docker push account/prjName:version'
  }
  
  stage('Run Docker container on remote server (SIT)') {
    def dockerRun = 'docker run -p 8443:8080 -d --name uni-controller syno/uni-controller:latest'
    sshagent(['privateKey']) {
      sh "ssh -o StrictHostKeyChecking=no usr@ip-add-123 ${dockerRun}"
    }
  }
  
  stage('Build project') {
    steps {
      echo '[START] Building project...'
      sh 'npm install'
      sh 'npm build'
      echo '[FINISH] Building project'
    }
  }
  
  stage("test") {
    echo '[START] Testing build...'
      
      //sh 'npm test'
      //sh 'npm build
    echo '[FINISH] Testing build'
  }
}
*/
