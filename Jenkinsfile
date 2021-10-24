
node{
stage('Checkout'){
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
			git branch: resp, url: 'https://github.com/jorgebarreiros-aet/ex3.git'
			
			return true
		   }
		catch(excp){
			return false
		}
	      }
	}
   }
}
