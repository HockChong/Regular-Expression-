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
```python:
# Create a dictionary
plan = { "field": courses[0], "tool": courses[1] }

# Complete the placeholders accessing elements of field and tool keys in the data dictionary
my_message = "If you are interested in {data[field]}, you can take the course related to {data[tool]}"

# Use the plan dictionary to replace placeholders
print(my_message.format(data=plan))

If you are interested in artificial intelligence, you can take the course related to neural networks
```

### Note: 
1. always specify whitespaces as `\s` to make sure match all forms of whitespace such as tabs, space or new line
```
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
`.` , `$` dun forget to use escape `\` for pattern matching


```
# Write a regex to match a valid email address
regex = r"[a-zA-Z0-9!#%&*\$\.]+@\w+\.com"

for example in emails:
  	# Match the regex to the string
    if re.findall(regex, example):
        # Complete the format method to print out the result
      	print("The email {email_example} is a valid email".format(email_example=example))
    else:
      	print("The email {email_example} is invalid".format(email_example=example))   
        
The email n.john.smith@gmail.com is a valid email
The email 87victory@hotmail.com is a valid email
The email !#mary-=@msca.net is invalid
```
