![License](https://img.shields.io/badge/License-MIT-blue.svg)

# Matching Email Regex

Table of Contents
  
  * [Description](#description)
  * [Anchors](#Anchors)
  * [Quantifiers](#Quantifiers)
  * [Grouping Constructs](#GroupingConstructs)
  * [Bracket Expressions](#BracketExpressions)
  * [Character Classes](#CharacterClasses)
  * [Character Escapes](#CharacterEscapes)
  * [License](#licenseSection)
  * [Github](#gitHub)
  * [Youtube Demo](#youtube)
  * [Contact](#Contact!)

### Description <a name="description"></a>
Welcome to this thorough tutorial on utilizing JavaScript to match email regular expressions (regex) in the realm of Computer Science. By the end of this guide, individuals ranging from beginners to seasoned academics will possess a comprehensive understanding of regex components, thanks to detailed explanations and example analyses. Throughout this tutorial, we'll explore email regex intricacies, dissecting the elements of a regex pattern tailored for validating email addresses. We'll elucidate how each component plays a vital role in guaranteeing precise and dependable email validation.
In this tutorial, we'll consistently refer to the highlighted regular expression (regex) shown below for thorough analysis of each regex component. This approach ensures that both newcomers and academics can grasp the material with utmost clarity. The regex components covered in this document encompass anchors, quantifiers, grouping constructs, bracket expressions, character classes, and character escapes.
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

### Anchors <a name="Anchors"></a>
Regular expressions serve as potent tools for identifying patterns in text. Anchors, unique characters within regular expressions, hold pivotal roles in establishing the position of the pattern within the input string. In email validation, exemplified by the regex featured in this tutorial, /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/, it's crucial to verify that the entire input string conforms to the specified pattern rather than just a segment of it.

There are two primary types of anchors:

Start Anchor ^: Asserts that the pattern must match the beginning of the string.
End Anchor $: Asserts that the pattern must match the end of the string.
Anchors essentially delineate the boundaries within which the regular expression should operate. For instance:

Example One: The regex ^hello$ exclusively matches the string "hello" and nothing else. It won't match "hello world" or "say hello" as the pattern isn't respectively at the start or end of the string.
Example Two: The regex ^hello matches any string where "hello" is at the string's outset. It'll match "hello" in "hello world" but not in "world hello" because the string doesn't commence with "hello".
Example Three: The regex hello$ matches any string where "hello" is at the string's end. It'll match "hello" in "world hello" but not in "hello world" because the string doesn't culminate with "hello".
In the realm of email validation, anchors are indispensable as they ensure adherence of the entire email address to the specified pattern. This precision is vital for accurate validation, forestalling partial matches or undesired outcomes. By demarcating boundaries at the string's commencement and conclusion, anchors ensure the pattern solely matches the intended text. They constitute critical elements in text processing pattern matching, especially pertinent in email address validation utilizing a regex like /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/. In summary, anchors are pivotal in determining the pattern's position within the input string, guaranteeing precise and dependable validation.

  
### Quantifiers <a name="Quantifiers"></a> 
In regular expressions (regex), quantifiers dictate the number of times a pattern should match, placed after a character, character class, or group to specify the minimum and maximum occurrences of the preceding pattern.

The + quantifier signifies "one or more," applied after the pattern [a-z0-9_.-] in the first capturing group ([a-z0-9_.-]+). It denotes that the pattern [a-z0-9_.-] should appear at least once, allowing for multiple consecutive occurrences. Consequently, the group matches one or more lowercase letters, digits, underscores, dots, or hyphens.

Similarly, the + quantifier follows the pattern [\da-z.-] in the second capturing group ([\da-z.-]+), matching one or more digits, lowercase letters, dots, or hyphens.

The {2,6} quantifier follows the character class [a-z.] in the third capturing group ([a-z.]{2,6}), matching a sequence of 2 to 6 lowercase letters or dots. This ensures that the email address concludes with a top-level domain comprising two to six letters, such as .com, .edu, or .co.uk.

In summary, the regular expression /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/ validates a correct email address that starts with one or more lowercase letters, digits, underscores, dots, or hyphens, followed by the @ symbol, followed by one or more digits, lowercase letters, dots, or hyphens, culminating in a period and a top-level domain spanning two to six letters.

Example: Quantifiers in regex determine the occurrences of a pattern, placed after characters, character classes, or groups. For instance, in the regex /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/:

Quantifier + matches "one or more" occurrences:
([a-z0-9_.-]+): Matches one or more lowercase letters, digits, underscores, dots, or hyphens.
([\da-z.-]+): Matches one or more digits, lowercase letters, dots, or hyphens.
Quantifier {2,6} matches between 2 and 6 occurrences:
([a-z.]{2,6}): Matches a sequence of 2 to 6 lowercase letters or dots.
This regex validates email addresses comprising:

One or more lowercase letters, digits, underscores, dots, or hyphens,
Followed by the @ symbol,
Succeeded by one or more digits, lowercase letters, dots, or hyphens,
Concluded with a period,
Ending with a top-level domain of two to six letters (e.g., .com, .edu, .co.uk).



### Grouping Constructs <a name="GroupingConstructs"></a>
Grouping constructs within regular expressions (regex) serve to consolidate one or more characters or sub-expressions, treating them as a singular unit within the expression. Enclosed within parentheses (), they fulfill several functions:

Applying quantifiers to a group of characters.
Capturing a specific part of the match for future use.
Creating a backreference for a previously matched group.
Applying alternation to a group of characters.
Our featured regex in this tutorial: /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/ comprises (3) grouping constructs enclosed within parentheses (). Each group captures a distinct segment of the email address: 1. Local-Part, 2. Domain, and 3. Top-level Domain.

The Local-Part ([a-z0-9_.-]+) initially matches the username of the email address. Subsequently, the Domain ([\da-z.-]+) corresponds to and matches the domain name. Lastly, the Top-Level Domain ([a-z.]{2,6}) aligns with and matches the top-level domain.

### Bracket Expressions <a name="BracketExpressions"></a>
Bracket expressions are a core component of regular expressions (regex), serving to specify a group of characters that can be matched within a single position in a text string. They are represented by square brackets [...], where any character enclosed within them becomes part of the allowable set. Bracket expressions can encompass individual characters and even define character ranges using a hyphen -, such as a-z for lowercase letters or 0-9 for digits. Their purpose is straightforward: bracket expressions enable the creation of adaptable patterns that can match various combinations of characters in the target text.

### Character Classes <a name="CharacterClasses"></a>
Character classes, also referred to as character sets, offer a concise means within regular expressions (regex) to represent specific sets of characters. By leveraging character classes, regex patterns can be simplified and condensed, enhancing readability and comprehension.

In the regex highlighted in this tutorial: /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/, diverse regex elements are employed, including character classes, character sets, metacharacters, and repeating character classes. These components are instrumental in ensuring accurate assessment and sourcing of the regex to match email addresses.

### Character Escapes <a name="CharacterEscapes"></a>
Character escapes are a crucial component of regex, facilitating precise pattern matching by neutralizing the special significance of metacharacters and representing characters that cannot be directly input. Within the context of our highlighted regex in this tutorial, /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/, we observe the utilization of character escapes.

ie.
Backslash:
The backslash serves as a common escape character in regex, enabling the treatment of metacharacters as literal characters. In our featured regex, the dot (.) is preceded by a backslash, as seen here: .. This ensures that the dot is interpreted as a literal period rather than as a metacharacter with a wildcard meaning.


![Alt Text](./assets/Screenshot)


  
#### Project License: MIT <a name="licenseSection"></a> 
https://opensource.org/licenses/MIT

### Github <a name="gitHub"></a>

https://github.com/yoboyyash/Yash-s-Regex-Js-README <br>
   
### Youtube <a name="youtube"></a>
Youtube demo for this project: 

https://youtube.com 

# Contact me! <a name="Contact!"></a> 

Yash Baviskar: yashrajbaviskar@gmail.com
