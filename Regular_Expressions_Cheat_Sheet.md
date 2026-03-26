---
title: "Regular Expressions Cheat Sheet"
tags: [linux]
sidebar: home_sidebar
permalink: regex.html
summary: Regular Expressions Cheat Sheet
keywords: regex, wildcard, repetition, character classes, boundary, replace, find, grep, posix
---

## Wildcards

| Pattern | Meaning |
| --- | --- |
| `.` | Any character |
| `\w` | Word character: letters, numbers, and `_` |
| `\W` | Non-word character |
| `\s` | White space: space, tab, or end of line (EOL) |
| `\S` | Non-white space character |
| `\d` | Digit character, but not the `.` in `2.4` |
| `\D` | Non-digit character |
| `\t` | Tab character |
| `\n` | Newline character, though some tools use `\r` |
| `\\` | `\` is the escape character, so `\\` matches `\`, `\^` matches `^`, and so on |

## Repetitions

| Pattern | Meaning |
| --- | --- |
| `*` | Match 0 or more times |
| `+` | Match 1 or more times |
| `?` | Non-greedy: get the shortest match |
| `{n}` | Match exactly `n` times |
| `{n,}` | Match at least `n` times |
| `{n,m}` | Match at least `n`, but not more than `m` times |

## Character Classes

| Pattern | Meaning |
| --- | --- |
| `[AEIOU]` | Match 1 vowel character |
| `[A-Z]` | Match 1 capital letter |
| `[A-Za-z0-9_]` | Same as `\w` |
| `^[A-Za-z]` | Match 1 letter at the beginning of a string or line |
| `[^A-Za-z]` | Match any character that is not a letter, including EOL. Note the very different meaning here. Inside `[]`, `^` means NOT. |

## Boundary Qualifiers

| Pattern | Meaning |
| --- | --- |
| `^` | Match at the start of a string or line |
| `$` | Match at the end of a string or line |
| `^ABC$` | Exact match to `ABC` - Both starts and ends in ABC|

## Capturing And Replacing

| Pattern | Meaning |
| --- | --- |
| `()` | Capture the search results between parentheses and save for later use. If there are multiple or nested groups, numbering follows the order of `(`. |
| `$1`, `$2` | Variables containing captured text, numbered by the order of `(`. These can be used in replacements. Some editors, such as BBEdit, use `\1`, `\2`, and so on. |

## Some Examples

Sample text: **This is 1.0 (one) line to play with**

| Pattern | Matches | Notes
| --- | --- |
| `\w*` | This |
| `\d+` | 1 |
| `[0-9\.]+` | 1.0 |
| `((\w*)\s(\w*))` | `$1` = "This is", `$2` = "This", `$3` = "is" |
| `\w*$` | with |
| `is\s{2}` | is is | from "Th**is is**" |
| `\(.+\)` | (one)  |Note the escaping of the parentheses |
| `\w+?` | T |Note the non-greediness of `?` |
| `\w*?` | Blank match | Why? |