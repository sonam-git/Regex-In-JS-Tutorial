# Chapter 01: Matching an Email

Welcome to this comprehensive tutorial on matching email regular expressions (regex) using JavaScript in the field of Computer Science. Upon completing the tutorial, both newcomers and academics alike will have a clear comprehension and understanding of regex components, achieved through detailed explanations and example analysis. In this tutorial, we will delve into email regex, breaking down the components of a regex pattern designed to validate email addresses and explaining how each part contributes to ensuring accurate and reliable email validation.

## Summary

This tutorial focuses on explaining and analyzing a featured regular expression (regex). It covers various regex components such as anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. The goal is to provide clear understanding and clarity to newcomers and academics. The tutorial aims to ensure that readers can comprehend and grasp the material effectively.
 ***Regex Featured in This Tutorial:***
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
<br>

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes & Character Sets](#character-classes-and-character-sets)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Character Escapes](#character-escapes)
- [Conclusion](#conclusion)
- [Author](#author)



## Regex Components
The tutorial discusses various components of regular expressions (regex).These components are essential building blocks of regular expressions and provide flexibility in defining patterns and matching criteria. Understanding and utilizing these components effectively can help in creating powerful and precise regex patterns.

### Anchors
Regular expressions are robust instruments for detecting patterns in text. Anchors, which are distinct characters in regular expressions, have a vital function in establishing the pattern's location within the input string. In the realm of email validation, as exemplified by the provided regex`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, it is imperative to verify that the complete input string aligns with the designated pattern, not just a portion of it.

**Anchors Come in (2) Main Types:**
1. Start Anchor `^`: This asserts that the pattern must match the start of the string.
2. End Anchor `$`: This asserts that the pattern must match the end of the string.

Anchors essentially define the boundaries of the text that the regular expression should match. 
<br>
**Example One:** the regex `^hello$` matches only the string "hello" and nothing else. It won't match "hello world" or "say hello" because the pattern is not at the start or end of the string, respectively.
<br>
**Example Two:** the regex ^hello matches any string where "hello" is at the start of the string. It will match "hello" in "hello world", but it will not match "hello" in "world hello" because the string does not start with "hello".
<br>
**Example Three:** the regular expression hello$ matches any string where "hello" is at the end of the string.  It will match "hello" in "world hello" but it will not match "hello" in "hello world" because the string does not end with "hello".

Anchors are extremely valuable in email validation because they play a crucial role in ensuring that the entire email address precisely conforms to the specified pattern. They are essential for achieving accurate validation by preventing incomplete matches or undesired outcomes. By establishing boundaries at the beginning and end of the text, anchors guarantee that the pattern only matches the intended content. These anchors are fundamental elements in text processing when it comes to validating email addresses using a regular expression such as `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. Ultimately, anchors contribute significantly to determining the position of the pattern within the input string and facilitate precise and dependable validation.


### Quantifiers
In regular expressions (regex), quantifiers are utilized to specify the desired number of matches for a given pattern. These quantifiers are positioned after a character, character class, or group, allowing control over the minimum and maximum occurrences of the preceding pattern.

The + quantifier, employed after the pattern `[a-z0-9_\.-] `in the initial capturing group `([a-z0-9_\.-]+)`, indicates that the pattern should appear at least once, but it can also repeat consecutively. Consequently, the group will match one or more lowercase letters, digits, underscores, dots, or hyphens.

Similarly, the + quantifier is used after the pattern `[\da-z\.-]` in the second capturing group `([\da-z\.-]+)`. This group matches one or more digits, lowercase letters, dots, or hyphens.

The `{2,6}` quantifier follows the character class `[a-z\.]` in the third capturing group `([a-z\.]{2,6})`. This group matches a sequence of 2 to 6 lowercase letters or dots, indicating that the email address must end with a top-level domain consisting of two to six letters or dots, such as .com, .edu, or .co.uk.

In summary, the complete regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`is designed to match a valid email address. It begins with one or more lowercase letters, digits, underscores, dots, or hyphens, followed by the @ symbol, then by one or more digits, lowercase letters, dots, or hyphens. Finally, it requires a period and a top-level domain of two to six letters or dots.

### OR Operator
The OR operator, also known as alternation, is indeed a significant concept in regular expressions. It allows for defining alternative patterns within a regex by using the | symbol. This enables the regex to match either one pattern or another. However, in the specific regex mentioned in this tutorial `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/`, the OR operator is not utilized or explicitly present. It's important to be aware of the OR operator for future use, as it becomes particularly useful when dealing with more complex patterns in your academic or professional endeavors.

The OR operator, denoted by the vertical bar `(|)`, is used in regular expressions to specify alternative patterns. It enhances the flexibility and matching capabilities of the regex by allowing it to match one pattern or another.

The syntax of the OR operator involves using the vertical bar to separate the alternative patterns within the regex. For instance, consider the regex `^(Apple|Banana)$`, which matches either the string `"Apple"` or `"Banana"`, but not both or any other strings.

The OR operator is an essential tool in regular expressions as it enables the creation of versatile and adaptable patterns. It allows regex users to define multiple options within a single expression, expanding the possibilities of pattern matching.

While the OR operator is not explicitly used in the featured email regex `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/`, it remains a fundamental concept for individuals learning and utilizing regular expressions in various applications. Understanding and employing the OR operator enhances the capabilities of regex and empowers users to handle more complex matching scenarios.

### Character Classes and Character Sets:
Character classes, also known as character sets, are an important component of regular expressions (regex) that represent specific sets of characters. They provide a concise and efficient way to define patterns by simplifying the regex and making them more readable.

In the regex featured in this tutorial `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/`, various regex elements are employed, including character classes, character sets, metacharacters, and repeating character classes. These elements ensure that the regex accurately matches email addresses.

The regex utilizes two primary character classes: `\d` and `..` Character sets are defined within square brackets, such as `[a-z]`, `[0-9]`, and `[.-]`. These sets represent multiple characters and allow matching a single character from the specified range.

### Negated Character Classes:
The negated character classes, denoted by a caret `(^)` symbol inside square brackets (e.g., `[^a-z]`), are not present in this email regex. However, they would match any character that is not a lowercase letter from `a to z`.

### Metacharacters Inside Character Classes:
Certain metacharacters, such as the dot (.), have special meanings in regex. However, when placed inside character classes, some metacharacters lose their special meaning and are treated as literals. In the featured email regex, the dot is escaped with a backslash `(.)` and the hyphen `(-)` is used as a literal character without escaping when placed at the beginning or end of the character set.

### Repeating Character Classes:
The email regex utilizes the + and {2,6} quantifiers to indicate repeating character classes. The plus sign `+` matches one or more occurrences of the preceding character class or set (e.g., `[a-z0-9_.-]+ and [\da-z.-]+`). The curly braces `{2,6}` define a specific range of repetitions for the preceding character class or set (e.g., `[a-z.]{2,6}`), matching `2 to 6` occurrences of lowercase letters or the literal period (dot) characters.

In summary, the combination of these elements in the featured regex ensures accurate sourcing and validation of email addresses by representing the required character sets in a clear and organized manner.

### Flags
Flags in regular expressions (regex) are modifiers that affect the behavior of the pattern by enabling or disabling specific features. They are appended to the end of the regex pattern, outside the forward slashes (/).

Although the regex featured in this tutorial `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` does not utilize any flags, it is important to understand their purpose in regex patterns. Flags allow you to control case sensitivity, multiline matching, global matching, and other functionalities. Familiarizing yourself with flags will help you expand your regex knowledge and adapt patterns to various requirements.

### Here are some flag types you may encounter in the future:
1. `g` (global): Enables global matching, allowing the regex engine to find all matches in the input string.
2. `i`  (ignore case): Enables case-insensitive matching, allowing the regex to match both uppercase and lowercase characters.
3. `m` (multiline): Enables anchors (^ and $) to match at the beginning and end of each line in a multiline string, rather than just at the start and end of the entire string.
4. `s` (dotAll): Enables the dot (.) metacharacter to match any character, including newline characters.
5. `u` (unicode): Treats the input string as Unicode and ensures proper handling of Unicode surrogate pairs.
6. `y` (sticky): Requires the regex engine to start searching for a match at the exact position specified by the lastIndex property.

In summary, flags are essential for modifying the behavior of regex patterns. Although not utilized in the regex featured in this tutorial, understanding the use of flags will empower you to adapt regex patterns to different requirements and scenarios.

### Grouping and Capturing
Grouping and capturing in regular expressions (regex) allow you to treat multiple characters as a single unit and extract specific portions of a matched pattern. They are represented by parentheses in the regex pattern. Here's an explanation of how grouping and capturing work:

Grouping allows you to create a subexpression within the regex pattern. It is denoted by enclosing the desired characters or subpattern in parentheses. By grouping characters together, you can apply quantifiers, alternations, or other regex constructs to the entire group instead of individual characters. It helps define the scope and precedence of certain regex operations.

Capturing allows you to extract specific portions of a matched pattern. It works in conjunction with grouping by designating a capturing group. When a match occurs, the content matched by a capturing group is stored in a numbered reference or captured group. These captured groups can be accessed using indices or references.

### Bracket Expressions
Bracket expressions are indeed a fundamental concept in regular expressions (regex) used to define sets of characters that can be matched within a single position in a text string. They are denoted by square brackets [...], and any character enclosed within these brackets becomes part of the allowed set. The purpose of bracket expressions is to create flexible patterns that can match various combinations of characters in the target text.

By using bracket expressions, you can define a specific set of characters that you want to match at a particular position in the text. For example, [a-z] represents all lowercase letters from `'a'` to `'z'`, and `[0-9]` represents all digits from `0 to 9`. You can include multiple individual characters or define character ranges using a hyphen (-) within the brackets.

Bracket expressions allow you to specify a range of characters or a set of characters that you want to match, providing flexibility in pattern matching. They enable you to define patterns that match different combinations of characters in a concise and efficient manner.

In our **regex featured in this tutorial:** `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` there are three (3) main bracket expressions:

### Bracket Expression: One (1)
The bracket expression [a-z0-9_\.-] matches any single character that falls within the range of lowercase letters a-z, digits `0-9`, or the characters` _, ., or -` .This expression is used to match the "local part" or the username part of an email address. Here's a breakdown of the components within this expression:
- `a-z`: Matches any lowercase letter from `a` to `z`.
- `0-9`: Matches any digit from `0` to `9`.
- `_`: Matches any underscore character.
- `\.`: Matches literal period (dot) character. The backslash is used to escape the dot since it has a special meaning in regex.
- `-`: Matces the hyphen character.

### Bracket Expression: Two (2)
The bracket expression `\da-z\.-`matches any single character that falls within the range of digits `0-9`, lowercase letters `a-z`, or the characters `.`, or `-`. This expression is used to match the "domain" part of an email address. Here's a breakdown of the components within this expression:

- `\d`: Matches digit from `0` to `9`. This is a shorthand for `[0-9]`.
- `a-z`: Matches lowercase letter from `a` to `z`.
- `\.`: Matches the literal period (dot) character.
- `-`: Matches hyphen character.

### Bracket Expression: Three (3)
The bracket expression `[a-z\.]{2,6}` matches any single character that falls within the range of lowercase letters `a-z` or the literal period (dot) character. This expression is followed by the quantifier {2,6}, which specifies that the matched characters should occur between `2 and 6`times, inclusive. This expression is used to match the "top-level domain" part of an email address. Here's a breakdown of the components within this expression:

- `a-z`: Matches lowercase letter from 'a' to 'z'.
- `\.`: Matches literal period (dot) character.
- `{2,6}`: Matches quantifier that specifies the number of times the preceding expression (i.e., `[a-z\.]`) must be matched, which is between `2 and 6` times, inclusive.

In summary, the featured regex`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` effectively matches valid email addresses by utilizing bracket expressions to define sets of characters for the username, domain, and top-level domain parts of the email address. These bracket expressions, combined with other regex components, ensure proper structure and format for email addresses, making it a valuable tool in various applications.

### Greedy and Lazy Match
The regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`does not contain any explicit greedy or lazy match modifiers. However, it's worth noting that by default, regular expressions are greedy, meaning they match as much as possible. In the context of email validation, this means that each part of the email address (username, domain, and top-level domain) will match the longest possible sequence of valid characters.

If you want to modify the matching behavior to be lazy (matching the shortest possible sequence), you can use the ? modifier after the quantifiers. However, in the given regex, the use of `?` would not be necessary or appropriate, as you typically want to match the entire email address without stopping prematurely.

In conclusion, the regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` follows the default greedy matching behavior, ensuring that each part of the email address matches the longest possible valid sequence of characters.

### Boundaries
boundaries are used to define specific positions in a string where matches can occur. Boundaries allow you to specify conditions such as the beginning or end of a line, word boundaries, or positions before or after certain characters. They do not consume any characters; instead, they represent positions in the input string.

### Back-references
The regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` does not contain any explicit back-references. Back-references are used to refer back to previously matched groups within a regular expression. They allow for matching repeated or duplicated patterns.

In the given regex, there are three capturing groups denoted by the parentheses `( )`. Each capturing group captures a specific part of the email address: the username, the domain, and the top-level domain. However, there are no explicit references or repetitions of these capturing groups within the regex.

The purpose of the capturing groups in this regex is to extract the respective parts of the email address for further processing or validation. The captured values can be accessed using back-references in programming languages or regex libraries that support them.

To summarize, while the regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` utilizes capturing groups to extract different parts of the email address, it does not contain any explicit back-references within the pattern itself.

### Look-ahead and Look-behind
The regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` does not include any look-ahead or look-behind assertions. Look-ahead and look-behind are advanced concepts in regular expressions that allow for matching patterns based on conditions that are ahead or behind the current position in the text.
Look-ahead assertions, denoted by `(?=...)`, allow you to assert that a pattern exists ahead of the current position without including it in the match. Look-behind assertions, denoted by `(?<=...)` or `(?<!...)`, allow you to assert that a pattern exists behind the current position without including it in the match.

In the given regex, there are no explicit look-ahead or look-behind assertions used. Instead, the regex focuses on capturing the different parts of the email address using capturing groups and specifying the allowed character sets and quantifiers for each part.

To summarize, the regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` does not employ look-ahead or look-behind assertions to match the email address pattern. It relies on capturing groups and character sets to validate and extract the different components of the email address.

### Character Escapes
Character escapes are an essential aspect of regex, allowing for accurate pattern matching by suppressing the special meaning of metacharacters and representing characters that cannot be directly typed. In our regex featured in this tutorial `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` we can identify the use of character escapes and their purposes:

### Backslash (\):
The backslash is a common escape character used to treat metacharacters as literals in regex. Throughout our featured regex, the dot `(.)` is escaped with a backslash, exactly like this` \..` Thus ensuring the dot is treated as a literal period instead of a metaphorical wildcard.

### Metacharacters:
Metacharacters have siginifcant meaning in regex, such as the dot `(.)`, plus sign `(+)`, and caret `(^)`. When placed among character classes, they often lose their special meanings and behave as though they are regular characters... In our featured email regex, the hyphen `(-)` is used as a literal character inside the character classes `[a-z0-9_\.-]` and `[\da-z\.-]` without needing to be escaped.

### Escape sequences:
Escape sequences, are characters that can not be directly typed or represented in a string, so escape sequences are the implemented, then used. These sequences start with a backslash `(\) `followed by a letter or combination of letters. In the email regex, `\d` is an escape sequence that represents any digit from `0 to 9`, serving as a shorthand for the use of `[0-9]`.

Character escapes serve a crucial role for ensuring accurately matching text patterns by interpreting special characters as literals. They help suppress the special meanings of metacharacters and represent characters that can't be directly typed. Thereby, ensuring the proper functioning of regex expressions that contribute to reliable email validation.

### Conclusion
Indeed, the email matching regex `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/` featured in this tutorial is effective in validating the structure of email addresses. Its various components work together to achieve this functionality:

* Anchors: The `^ `and $ anchors ensure that the matching occurs from the start to the end of the string, respectively.
* Quantifiers: The` +`and `{2,6}` quantifiers specify the number of times a preceding character or group should appear. They ensure that there are valid sequences of characters in the email address.
* Grouping Constructs: The parentheses `()` capture and group certain parts of the email address, allowing for easier extraction or referencing of those parts.
* Bracket Expressions: Square brackets `[]` define character sets, such as `[a-z0-9_.-] and [\da-z.-],` which specify the allowed characters in the username and domain parts of the email address.
* Character Classes: The `\d `character class represents any digit, while . represents the literal period (dot). They help match specific characters within the email address.
* The OR Operator: Although not used in this regex, the OR operator `(|)`can be employed to provide alternative patterns when matching specific parts of the email address.
* Flags: No flags are used in this regex, but they can be added to modify the pattern matching behavior, such as making it case-insensitive with the i flag.
* Character Escapes: The backslash `()` is used to escape special characters like the period, treating them as literal characters rather than metacharacters.

By combining these components, the regex ensures that the email address follows the expected structure and format. It provides a valuable tool for validating and confirming the entry of valid email addresses in various academic and professional contexts. Through this tutorial, you will gain a deeper understanding of regex and its role in email validation.

## Author
Follow me on Github at [Sonam J Sherpa](https://github.com/sonam-git).
Additional questions or concerns? feel free to contact me at sherpa.sjs@gmail.com