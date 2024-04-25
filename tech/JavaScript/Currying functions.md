https://medium.com/madhash/what-is-currying-in-javascript-and-why-does-it-matter-db5926fc4f42

When a function returns another function to process the next parameter 

```
your_currying_function(param1)(param2)(param3)

function your_currying_function(param1){

	return(param2){
		# do something with param1 output
		
		return(param3){
			# do something with param2 output
			
			return finalResult
		}
	}
}
```
