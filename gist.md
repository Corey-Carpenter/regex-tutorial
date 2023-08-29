# Regular Expression Functions

There are many ways to determine if a string contains a phrase, or ends with a specific word, or starts with a specific letter/number. Regex functions, or regular expression functions, are an extremely useful tool that is far more dynamic and usually shorter. They are perfect for data validation. If you need to verify someone's email, or phone number, or IP address, or anything else, regex functions are a great tool. The regex functions can seem intimidating at first, but once you understand how they work, using them becomes far easier. 

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Character Classes](#character-classes)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Example](#example)
- [Author](#author)

## Regex Components
Regexes are not just one big blob of nonsense, but multiple differents components that all work together to validate data. They validate data through a specific search pattern that the components provide. The most common components are anchors, quantifiers, character classes, and alterations. 

### Anchors
Anchors are probably the simplest components of a regex function. They essentially determine the beginning and ending points of a string. For the beginning, a \^ (caret) symbol is used, and for the ending, a \$ (dollar sign) symbol is used. Also, an important thing to note is that there needs to be a \/ at the very start and end of regex functions. For example: /^[whatever search parameters you want]$/

### Character Classes
Character classes let you determine specific groups of characters you would want to match. They are always closed in square brackets []. For example if you want the string to be able to have any lowercase between a and z you'd write [a-z]. If you want digits you could write [0-9].

### Quantifiers
Quantifiers specify how frequently a preceding element in a regex pattern should appear. They have influence over character or group repetition. Using specific symbols allows you to customize search parameters. Here are a few examples: An asterisk * matches 0 or more occurences. A plus sign + matches 1 or more occurences. A question mark ? matches zero or one occurences. Using curly brackets you can also matches specific number n occurences: {n}. Putting a comma after n matches n or more occurences: {n,}. Using two numbers will match between them: {n,m}. 

### OR Operator
The OR operator is |, the vertical bar(not i). The OR Operator is great for things that can be spelled differently across the world. A great example of this is color/colour. They both mean the same thing but are spelled differently. Instead of having two completely different regex functions you can use the OR | operator: (r|ur). It basically means whatever is on the left of the operator, or on the right both work. 

### Flags
Flags are used to modify how a regex pattern is interpreted. For example the 'i' flag means that it is case-insensitive. The 'g' flag means global matching, or finding all occurences. 

### Grouping and Capturing
Grouping and catching use () parentheses to group parts of a pattern. They capture the text you grouped with the parentheses, allowing you to use it later. 

### Bracket Expressions
Bracket expressions are also known as character classes, and they're a fundamental component of regex functions that let you choose a set of characters from which you want to match a single character. They are inclosed in square brackets []. A basic example: [abc] - this matches any single character that is either 'a', 'b', or 'c'. A very common way of using this is with ranges. Example: [a-z0-9] - this matches any lowercase letter and any digit. You can also do uppercase. Another way to do this is with negation. Example: [^0-9] - using a ^ caret beforehand matches anything that is not a digit. You can also put in special characters like a hyphen or underscore.

### Greedy and Lazy Match
Greedy basically means they match as much text as possible. Quantifiers for example are inherently greedy. Lazy is the opposite, matching as little as possible. To make a quantifier lazy add a question mark ? after it. For example:  (*?, +?, ??, {n,}?) 

### Boundaries
Boundary assertions aid in discovering matches based on position in the text rather than on the characters themselves. It used using a backslash \. For example: '\b' means there is a word boundary and '\B' means there isn't a word boundary. 

### Back-references
Back-references enables you to match the same text that was previously collected by a capturing group earlier in the pattern. They help you spot recurring patterns and guarantee consistency in your regex matches. However, there's a problem with back references in that not all regex engines support them. So make sure to read the documentation around what you're making to make sure you can use them. 

### Look-ahead and Look-behind
Look-ahead and look-behind assertons let you check for patterns ahead or behind the current position. It does not consume characters. Look-ahead is written as: ((?=...)) and look-behind is very similar but with an angle bracket <> going backwards: ((?<=...)).

### Example
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ 
This regex function is used to match and validate an email address. It starts with the caret ^ and ends with the dollar sign $. 

'([a-z0-9_\.-]+)': This part is a capturing group that matches the username before the @ symbol. The plus sign is a quantifier that means the preceeding character set needs to appear one or more times. It takes lowercase letters, digits, undersores, hypherns, and periods. The @ symbol is being matched after the username and before the domain name.

([\da-z\.-]+): This is another capturing group that matches the domain name(not the top-level domain). the \d represents any digits, which isn't super necessary because most domain names don't have numbers. This takes any lowercase letters, digits, hyphens, and periods. The plus sign + once again means that the preceesing character set has to occur one or more times. 

\.: The backslash period matches an actual period. It is used to seperate the domain name from the top level domain: @gmail . com for example.

([a-z\.]{2,6}): This is the capturing group for the top level domain: the .com, .net. etc. This character set includes lowercase letters and a period. the {2,6} is there to specify that the preceeding character set happens between 2 and 6 times. And like I mentioned before the dollar sign $ ends the regex function.


## Author
My name is Corey Carpenter and I'm learning how to code in the hopes I can create an application I can sell. I'm currently 19 years old as of 2023 and I really enjoy coding so far. My [Github](https://github.com/Corey-Carpenter) has all the projects I've worked on so far. Nothing terribly fancy or overly complicated but it is definitely a good start.
