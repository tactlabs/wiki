/ [Home](index.md)

## TactLabs Repo Standard

**Note:** Following some rules will make us to create a better group



### Repo Standard
- Every repo should be in lowercase and - should be used instead of _ or space
- Every repo should have readme.md file
- readme.md should explain about the project in 2-3 lines
- readme.md should explain how to run the project
- Every repo should have .gitignore file 
- For sample .gitignore, check here: [.gitignore](https://wiki.tactii.com/gitignore.html)
- Every Python repo should contain .env ad .env.sample (if any sensitive info used in the project)
- Every Python repo should contain requirements.txt file
- if requirements.txt available, it should have clear version mentioned (sample: flask==1.2.2)
- Team leads should take the responsibility to make sure the team is following the standards


Examples:
```
	branch: Testimonial-page - is wrong
	branch: testimonial-page - is right

	html: Quote.html - is wrong
	html: quote.html - is right

	html: Webinar_one.html - is wrong
	html: webinar-one.html - is right
```