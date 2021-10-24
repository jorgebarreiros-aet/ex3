
node{
stage('Checkout'){
    def resp
   
    try{
    timeout(time: 30, unit: 'SECONDS') {
      resp = input message: 'Input branch name’, 
                   submitterParameter: ‘submitter’, 
		               parameters: [string(defaultValue: 'main’, 
			                          description: ‘Name of branch to checkout’, 
			                          name: 'branchName’, 
			                          trim: true)]
   }
   catch(except){
      resp='main';
   }
   
   
   }
