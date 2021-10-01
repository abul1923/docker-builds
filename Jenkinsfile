node {   
    stage('Checkout the dockefile from GitHub') {            
      git branch: 'mycodes', 
          url: 'https://github.com/abul1923/docker-builds.git'        
    }
     
    stage('Build the Image and Push to Docker hub') {                
      app = docker.build('abulhassan/web-server')                
      withDockerRegistry([credentialsId: 'docker']) {                
      app.push("${env.BUILD_NUMBER}")                
      app.push('latest')
     }        
    }    
}
