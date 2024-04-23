# Regex Tutorial on Matching a Hex Value

What is regex? Well, if you are new to coding, you might see this strange word pretty often. Regex stands for "regular expression", but this name is also somewhat misleading since it is not the tradional "expression" you might be thinking of. In fact, regular expressions look like daunting, random characters clustered together with no apparent meaning. Regardless of their seemingly odd look, regular expressions are actually a pattern of characters that do have a purpose and can actually be quite useful when trying to conduct a search for a specific value when you need it.

## Summary

I will be providing a breakdown on a regular expression on a value that you might have seen before at least once in your lifetime-the hex value. 
<br>
<strong>Hex Value Regex:</strong> `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`
</br>
Commonly used when websites allow the liberty to personalize your profile or account, a hex value is a useful string when you want to identify a unique color. That being said, I will now breakdown the various concepts being used in this regex such as anchors, grouping constructs, quantifiers, and bracket expressions.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [The OR Operator](#the-or-operator)

## Regex Components

 Before we dive in deeper, it is important to note that all regex components must begin and end with `/`.

### Anchors

If you haven't already noticed, `^` and`$` are present after and before the `/` slash, respectively. These are called <strong> anchors </strong>. Anchors, in our case, are used to tell where our string pattern will begin and end. For example, the beginning of our regex,`/^#`, lets us know that the string that is being searched for will contain the following hashtag <strong>#</strong>. We know this is true because all hex values such as #eea4bb and #b58 contain a hashtag.


### Bracket Expressions

Bracket expressions are anything wrapped inside brackets: `[]`. In our example, we have two expressions with the same value wrapped inside which is the following string `[a-f0-9]`. The first part to this expression is `a-f` which simply means that the regex is searching for a match of any possible range from the <strong>lowercase</strong> letters a to f. Knowing this, the second part of this expression, `0-9`, makes itself easier to understand because it then means that the regex is searching for a range of numbers from 0-9. Putting these two together will tell us that the regex is looking for <strong>any</strong> possible range of the specified lowercase letters and numbers! 

### Quantifiers

In the previous section, I mentioned about the two bracket expressions present that held the same value. Although almost the same, their difference in value is dependent on what is grouped next to them (`{6}` and `{3}`). These are called <strong>quanitifiers</strong>. These quantifiers tell the regex it will be looking for a match of either a possible combination of 6 or 3 of the following bracket expression `[a-f0-9]`. Again, this bracket expression specifies a match ranging from the lowercase letters a-f and numbers 0-9.

There is also one more character that can be classified as a quanitfier in our regex example. The other quantifer you see is given by the question mark `?` after the hashtag `#` in the beginning of the expression. The `?` quantifier, which is technically considered a <strong>greedy</strong> quanitfier, means that the preceding element (#) will need to be matched either 0 or 1 times.

### Grouping Constructs

Grouping constructs exist in our regex example and are usually bound within a pair of parenthesis `()`. So, in our case, our grouping construct currently looks like the following: `([a-f0-9]{6}|[a-f0-9]{3})`. The main purpose of having a grouping construct is to let the regex know it will be searching for an <strong>exact</strong> match. Now what does this mean for our particular example? Well, it simply means the regex is looking for an exact match of a string of either 6 or 3 alphanumeric characters with the specifications given within the bracket expressions.

### The OR Operator

Lastly, I will meantion the OR operator in the regex which is specificied with the `|` symbol. Now let's take a look at our whole regex again-`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. The OR operator, if you haven't noticed, is right in between our two bracket expressions `[a-f0-9]`. Using what I explained in the previous sections, the purpose of the OR operator should be a bit easier to guess now. If you still weren't able to guess it, then no worries! It really is just there to tell the regex it wants to find a string match containing 6 alphanumeric characters OR 3 alphanumeric characters.

## Author

Thank you for reading my gist. My name is Noelia and I am a new full-stack developer. Please check out my other repos on my page at: https://github.com/noe-bee