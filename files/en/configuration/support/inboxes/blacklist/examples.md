#### Examples:

    no-reply@gmail.com

    noreply@mail.com

    do not reply on this mail
    
    reply to this email

|Pattern         | Description                                                           |
|----------------|-----------------------------------------------------------------------|
|noreply         | Will filter second string                                |
|reply           | Will filter all strings                                  | 
|do.*?reply      | Will filter third string                                |
|no-*reply       | Will filter first and second strings                     |

**Some of special characters:**

Quantifiers:* + ? and {}

|Quantifier              | Description                                                                    |
|------------------------|--------------------------------------------------------------------------------|
|abc*                    | Matches a string that has ab followed by zero or more c                        |
|abc+                    | Matches a string that has ab followed by one or more c                         |
|abc?                    | Matches a string that has ab followed by zero or one c                         |
|abc{2}                  | Matches a string that has ab followed by 2 c                                   |
|abc{2,}                 | Matches a string that has ab followed by 2 or more c                           |
|abc{2,5}                | Matches a string that has ab followed by 2 up to 5 c                           |
|a(bc)*                  | Matches a string that has a followed by zero or more copies of the sequence bc |
|a(bc){2,5}              | Matches a string that has a followed by 2 up to 5 copies of the sequence bc    |

OR operator:| or []

|Operator | Description                                                              |
|---------|--------------------------------------------------------------------------|
|a(b&#124;c)   | Matches a string that has a followed by b or c                      |
|a[bc]    | Same as previous                                                         |

Character classes:

| Class | Description                                                                |
|-------|----------------------------------------------------------------------------|
| \d    | Matches a single character that is a digit                                 |
| \w    | Matches a word character (alphanumeric character plus underscore)          |
| \s    | Matches a whitespace character (includes tabs and line breaks)             |
| .     | Matches any character                                                      |