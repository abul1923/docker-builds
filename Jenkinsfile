node {   
    stage('Checkout the dockefile from GitHub') {            
      git branch: 'main', credentialsId: 'fourtimesId', url: 'https://github.com/FourTimes/demo-build.git'        
    }
     
    stage('Build the Image and Push to Docker hub') {                
      app = docker.build('jjino/demo')                
      withDockerRegistry([credentialsId: 'acr_credentials']) {                
      app.push("${env.BUILD_NUMBER}")                
      app.push('latest')
     }        
    }    
}
