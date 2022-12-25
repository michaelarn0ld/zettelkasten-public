# Technical Challenges of Zettel Service
The current problem that I must solve is how to best convert data of this form:
```
{
	"git_head": "7a9e369",
	"tags": [{
		"tag": "algorithms",
		"zettels": [{
			"zettel_id": "202201310445",
			"title": "STARTTITLE_# Big O Notation: Considerations_ENDTITLE"
		}, {
			"zettel_id": "202201310439",
			"title": "STARTTITLE_# Big O Notation: Time Complexity_ENDTITLE"
		}]
	}, {
		"tag": "zen",
		"zettels": [{
			"zettel_id": "202212020840",
			"title": "STARTTITLE_# Peace and Clarity_ENDTITLE"
		}]
	}]
}
```

Into this form:
```
    {
        id: 1,
        attributes: ["react"],
        content: "Configuring a React Application from Scratch",
        zetId: "202201191736"
    },

    {
        id: 2,
        attributes: ["linux"],
        content: "Basics of Stdin, Stdout, Stderr - Pipes & Redirection",
        zetId: "202110050602"
    },

    {
      id: 3,
      attributes: ["concurrency", "java"],
      content: "Getting the First Finished Future",
      zetId: "202209010626"
    }
```

Since each zettel should be unique, I am thinking I can basically just iterate
over each of the tags, and create a new Preview for each and add it to a Set. 
I will modify the HashCode of the Preview class so that it is represented by
the zettel id (since that is the unique portion of the zettel)

For every zettel (in every tag), I will check if that zettel is in the set. If 
it is, I will simply add the current tag to its attributes (if it is not there).
If it is not a member of the set, I will create a new Preview in the set with
the current tag as its only attribute.

I will probably need to add a method to the Preview class so that I can modify
its attributes member

## Tags
#tech #engineering
