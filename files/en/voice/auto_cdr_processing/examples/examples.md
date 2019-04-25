#### Examples:

    AB-CDR-20190201013000-1-0025B516891F-125464.csv

    BC-CDR-20190201013000-2-0025B516891C-125465.csv

    BC-CDR-20180201013000-3-0025B5168912-12546.csv

|Pattern         | Description                                                           |
|----------------|-----------------------------------------------------------------------|
|AB              | Will filter the file names that have 'AB' symbols                     |
|CDR             | Will match all 3 files                                                |
|2019            | Will match the first two files which contain '2019' in their names    |
|516891[A-Z]     | Will match the first two files with matches 516891F, 516891C          |
|516891[F2]      | Will match the first and the third files with matches 516891F, 5168912|
|516891[F2]-\d{6}|  Will match only the first one                                        |

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
