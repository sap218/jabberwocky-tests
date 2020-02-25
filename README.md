# jabberwocky-tests
tests for the jabberwocky toolkit - see [jabberwocky](https://github.com/sap218/jabberwocky) repository

---

### `catch`
see directory `catch` for the example test - **note**: code was performed in the directory
* `ontology/pocketmonsters.owl` is a very brief ontology with classes, including exact and related synonyms
* `listofwords.txt` is a list of terms a user wants to search with, these are exact same as those class labels
* `blogs.json` is file of user blogs - **note**: this was completely fabricated for the exampple
* `blog_post` is the key for the text, using this will collate the users' blog posts and ignore their names

**ontology, keywords, json file w/ parameter** - *this is the current `ontology_dict_class_synonyms.json` output* 

`$ catch --ontology ../ontology/pocketmonsters.owl --keywords listofwords.txt --textfile blogs_formatted.json --parameter blog_post > catch_output.txt`

**ontology, keywords, txt file, saves to file**

`$ catch -o ../ontology/pocketmonsters.owl -k listofwords.txt -t blogs_unformatted.txt`

**ontology, txt file**

`$ catch -o ../ontology/pocketmonsters.owl --textfile blogs_unformatted.txt`


---


### `bite`
see directory `bite` for the example test - **note**: code was performed in the directory
* `ontology/pocketmonsters.owl` is a very brief ontology with classes, including exact and related synonyms
* `public_forum` is the public forum example which will be used

**ontology, json file w/ parameter** - *this is the current `ontology_all_terms.txt` & `tfidf_results.csv` output* 

`$ bite -o ../ontology/pocketmonsters.owl -t public_forum.json -p post`

**json file w/ parameter** - *this will not remove any ontology terms and so output will be larger*

`$ bite -t public_forum.json -p post`


---


### `arise`
see directory `arise` for the example test - **note**: code was performed in the directory
* `ontology/pocketmonsters.owl` is a very brief ontology with classes, including exact and related synonyms
* `new_synonyms_tfidf.csv` is the new synonyms you want to add - based on the `bite` output
* `updated-ontology.owl` is the output 

`$ arise -ontology ../ontology/pocketmonsters.owl -tfidf new_synonyms_tfidf.csv`
`$ arise -o ../ontology/pocketmonsters.owl -f new_synonyms_tfidf.csv`


---
---


### process/
**Note**: during these steps I renamed files accordingly to display the differences
* `catch` using the ontology [pocketmonsters.owl], keywords [`listofwords.txt`], text data [public_forum.json] (& parameter) to `catch_01_output.txt` - current classes and synonyms are: `catch_01_ontology_dict_class_synonyms.json`
* `bite` using the text data (& parameter) - the full results are in `bite_01_tfidf_results` and then made `new_synonyms_tfidf.csv` based on it
* `arise` using the ontology and the `new_synonyms_tfidf.csv` file, providing `updated-ontology.owl` output
* `bite` ran a second time to oberve rewighing, provided the `updated-ontology.owl` and the text data (& parameter) - the full results are in `bite_02_tfidf_results` plus a list of all ontology class terms & synonyms in `bite_02_ontology_all_terms.txt`
* `catch` is the final step: using the `updated-ontology.owl`, keywords, text data (& parameter) to `catch_02_output.txt` - with newly updated classes and synonyms are: `catch_02_ontology_dict_class_synonyms.json`

```
$ catch -o ../ontology/pocketmonsters.owl -k listofwords.txt -t public_forum.json -p post > catch_01_output.txt
$ bite -t public_forum.json -p post
$ arise -o ../ontology/pocketmonsters.owl -f new_synonyms_tfidf.csv 
$ bite -o updated-ontology.owl -t public_forum.json -p post
$ catch -o updated-ontology.owl -k listofwords.txt -t public_forum.json -p post > catch_02_output.txt
```
