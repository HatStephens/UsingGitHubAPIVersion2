Using GitHub API - Version 2
=======================

## Synopsis

Having completed this task earlier in the week, I wanted to try and consolidate my understanding and re-do this project from scratch. I also wanted to try and improve my use of JSON API data and get commit data for each repository as well listing each repository.

## Technologies Used

HTML, CSS, jQuery, Handlebars

## Job List

- [x] Produce HTML Page
- [x] Style it using CSS
- [x] Create a template for use with Handlebars
- [x] Use jQuery to access API data (JSON)

## Favourite Code Snippet

```
 $.each(repositories, function(index){
								$.getJSON('https://api.github.com/repos/'+username+'/'+repositories[index].name+'/contributors?client_id=105a140f1cf546a14c96&client_secret=0720e817925e73b3f387ba2dcbe979b429a88309', function(jsoncom){
	    					  commits = jsoncom;                  
	    					 	 	$.each(commits, function(index){
	    					  		if(commits[index].login === username) {
	    					  		commitsNumber += commits[index].contributions;
	    					  		}
	    					  	});
	    								commitsHTML = '<p>'+commitsNumber+' commits!</p>';	
	          					$('#'+username+'commits').html(commitsHTML);
	  							}); 
	          	})
```

## Collaborators

None.

## Still to complete/refactor

- [ ] The page could easily be improved from a design/presentation point of view
- [ ] I could try and integrate this with Sinatra or Express to get this online
- [ ] The code could be refactored and cleaned up in some areas
- [ ] Unable to use Handlebars for all the templating and had to use jQueury.html() for some of this. It would be good to try and find out how Handlebars would be possible for these additions
- [ ] I would like to be able to enter my Makers Academy Cohort Name and see all 28 of us listed on the page