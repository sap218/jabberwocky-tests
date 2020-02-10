# jabberwocky-tests
tests for the jabberwocky toolkit - see [jabberwocky](https://github.com/sap218/jabberwocky) repository

### `catch`
see directory `catch` for the example test
* `ontology/pocketmonsters.owl` is a very brief ontology with classes, including exact and related synonyms
* `listofwords.txt` is a list of terms a user wants to search with, these are exact same as those class labels
* `blogs.json` is file of user blogs - **note**: this was completely fabricated for the exampple
* `blog_post` is the key for the text, using this will collate the users' blog posts and ignore their names


**ontology, keywords, json file w/ parameter** - *this is the current `ontology_dict_class_synonyms.json` output* 

`$ catch --ontology ontology/pocketmonsters.owl --keywords listofwords.txt --textfile blogs_formatted.json --parameter blog_post > catch_output.txt`


**ontology, keywords, txt file, saves to file**

`$ catch -o ontology/pocketmonsters.owl -k listofwords.txt -t blogs_unformatted.txt`


**ontology, txt file**

`$ catch -o ontology/pocketmonsters.owl --textfile blogs_unformatted.txt`
