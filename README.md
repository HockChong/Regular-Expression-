# Regular Expression

## Learning Resources 
1. https://regexr.com/
2. https://help.tableau.com/current/pro/desktop/en-us/functions_functions_additional.htm
3. https://regexr.com/
4. https://www.tableau.com/about/blog/2015/6/become-regular-regular-expressions-39802
5. https://www.linkedin.com/learning/learning-regular-expressions-2/write-text-matching-patterns
6. https://regex101.com/
7. https://regexone.com/
8. https://campus.datacamp.com/courses/regular-expressions-in-python


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
