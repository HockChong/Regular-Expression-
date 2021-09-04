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
```python:
# Assign the substrings to the variables
first_pos = wikipedia_article[3:19].lower()
second_pos = wikipedia_article[21:44].lower()

# Define string with placeholders 
my_list.append("The tool {} is used in {}")

# Define string with rearranged placeholders
my_list.append("The tool {1} is used in {0}")

# Use format to print strings
for my_string in my_list:
  	print(my_string.format(first_pos, second_pos))
```
