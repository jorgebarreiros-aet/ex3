
node{
stage('CheckoutSCM'){
    def resp
   
    try{
    timeout(time: 30, unit: 'SECONDS') {
          resp = input message: 'Input branch name', 
                   submitterParameter: 'submitter', 
		               parameters: [string(defaultValue: 'main', 
			                          description: 'Name of branch to checkout', 
			                          name: 'branchName', 
			                          trim: true)]
   	}
    }
   catch(except){
      resp='main';
   }
   
	timeout(time: 1, unit: 'MINUTES'){
		waitUntil{
		try{
			echo 'trying to get branch:'+resp['branchName']
			git branch: resp['branchName'], url: 'https://github.com/jorgebarreiros-aet/jenkins-helloworld.git'
			echo 'checkout successful'
			return true
		   }
		catch(excp){
			echo 'can\'t connect' 
			return false
		}
	      }
	}
   }
}
