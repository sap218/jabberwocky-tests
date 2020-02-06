# jabberwocky-tests
tests for the jabberwocky toolkit

### `catch`
see directory `catch` for the example test
* `ontology/pocketmonsters.owl` is a very brief ontology with classes, including exact and related synonyms
* `listofwords.txt` is a list of terms a user wants to search with, these are exact same as those class labels
* `blogs.json` is file of user blogs - **note**: this was completely fabricated for the exampple
* `blog_post` is the key for the text, using this will collate the users' blog posts and ignore their names


*ontology, keywords, json file w/ parameter*

`$ catch --ontology ontology/pocketmonsters.owl --keywords listofwords.txt --textfile blogs_formatted.json --parameter blog_post`


*ontology, keywords, txt file, saves to file*

`$ catch --ontology ontology/pocketmonsters.owl --keywords listofwords.txt --textfile blogs_unformatted.txt > catch_output.txt`


*ontology, txt file*

`$ catch --ontology ontology/pocketmonsters.owl --textfile blogs_unformatted.txt`
