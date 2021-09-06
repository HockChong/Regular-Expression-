# Regular Expression

## Learning Resources 
1. https://regexr.com/
2. https://help.tableau.com/current/pro/desktop/en-us/functions_functions_additional.htm
3. https://www.tableau.com/about/blog/2015/6/become-regular-regular-expressions-39802
4. https://www.linkedin.com/learning/learning-regular-expressions-2/write-text-matching-patterns
5. https://regex101.com/
6. https://regexone.com/
7. https://campus.datacamp.com/courses/regular-expressions-in-python


## Example 
Using dictionary in string formating.
```python
# Create a dictionary
plan = { "field": courses[0], "tool": courses[1] }

# Complete the placeholders accessing elements of field and tool keys in the data dictionary
my_message = "If you are interested in {data[field]}, you can take the course related to {data[tool]}"

# Use the plan dictionary to replace placeholders
print(my_message.format(data=plan))
```
```
If you are interested in artificial intelligence, you can take the course related to neural networks
```

### Note: 
1. always specify whitespaces as `\s` to make sure match all forms of whitespace such as tabs, space or new line
```python
# Write a regex to obtain number of retweets
print(re.findall(r"number\sof\sretweets:\s\d", sentiment_analysis))

['number of retweets: 7']
```
### Regex Match Pattern
Symbol | Descriptions
------------ | -------------
`\W`| all special characters
`\w`| Any Alphanumeric character
`*`| 	Zero or more repetitions
`+`|  Once or more repetitions
`?`| Zero or once repetitions
`\S` | pattern that starts with sequence with any Non-whitespace character
`^` | start of the string
`.` | any Character(except newline)

### Remarks
`.` , `$` , `(`, `)` dun forget to use escape `\` for pattern matching


```python
# Write a regex to match a valid email address
regex = r"[a-zA-Z0-9!#%&*\$\.]+@\w+\.com"

for example in emails:
  	# Match the regex to the string
    if re.findall(regex, example):
        # Complete the format method to print out the result
      	print("The email {email_example} is a valid email".format(email_example=example))
    else:
      	print("The email {email_example} is invalid".format(email_example=example))  
```
```
        
The email n.john.smith@gmail.com is a valid email
The email 87victory@hotmail.com is a valid email
The email !#mary-=@msca.net is invalid
```

- `re.match` vs `re.search` differences
https://docs.python.org/2/library/re.html?highlight=matching%20searching#search-vs-match
`re.match()` checks for a match only at the beginning of the string, while `re.search()` checks for a match anywhere in the string (this is what Perl does by default).
 MULTILINE mode match() only matches at the beginning of the string, whereas using search() with a regular expression beginning with '^' will match at the beginning of each line.
 
 - greedy quantifier ( `*` , `+` , `?`) will try to match as much as possible while a non-greedy quantifier (Append `?` to greedy quantiers to match as few characters as needed ) will do it as few times as needed, expanding one character at a time and giving us the match we are looking for.

- Capturing the group using `()`
- - include `?:` after the opening parenthesis of the non-capturing group in the regex. `(?:regex)`
``` python
# Write regex to capture information of the flight
regex = r"([A-Z]{2})(\d{4})\s([A-Z]{3})-([A-Z]{3})\s(\d{2}[A-Z]{3})"

# Find all matches of the flight information
flight_matches = re.findall(regex, flight)
    
#Print the matches
print("Airline: {} Flight number: {}".format(flight_matches[0][0], flight_matches[0][1]))
print("Departure: {} Destination: {}".format(flight_matches[0][2], flight_matches[0][3]))
print("Date: {}".format(flight_matches[0][4]))
```
```
Airline: IB Flight number: 3723
Departure: AMS Destination: MAD
Date: 06OCT
```
Using .group index start from 1. Only if you use .search() and .match(), you can use .group() to retrieve the groups.
Backreferences are very helpful when you need to reuse part of the regex match inside the regex. Knowing when and how to use them will simplify many of your tasks!
```python
html_tags = ['<body>Welcome to our course! It would be an awesome experience</body>',
 '<article>To be a data scientist, you need to have knowledge in statistics and mathematics</article>',
 '<nav>About me Links Contact me!']
 
 for string in html_tags:
    # Complete the regex and find if it matches a closed HTML tags
    match_tag =  re.match(r"<(\w+)>.*?</\1>", string)
 
    if match_tag:
        # If it matches print the first group capture
        print("Your tag {} is closed".format(match_tag.group(1))) 
    else:
        # If it doesn't match capture only the tag 
        notmatch_tag = re.match(r"<(\w+)>", string)
        # Print the first group capture
        print("Close your {} tag!".format(notmatch_tag.group(1)))
 ```
 ```
 Your tag body is closed
Your tag article is closed
Close your nav tag!
      
