# Commit Rules
In object-oriented programming, there are rules for collaboration, such as class names, variables, and method naming.  
Similarly, There are several commit rules for collaboration.

<br>

## Index
1. [Multiple lines of commit message](#1-multiple-lines-of-commit-message)
2. [Structure of commit message](#2-structure-of-commit-message)

<br>

## 1. Multiple lines of commit message
You can commit with a one-line commit message if you enter the command below.

    > git commit -m "<commit message>"

At this time, if you erase the large quotation mark(") at the end, you can enter multiple lines of commit message.

    > git commit -m "type: Subject
###
    body
###
    footer"

The last line must be marked with a double quotation mark(") at the end.

[▲ Top](#commit-rules)

<br>

## 2. Structure of commit message
Commit messages consist of type, title, body, and footer, each separated by a blank line.

    type: Subject

    body

    footer

### 2.1. Type
Type specifies the type of commit and can be one of these types:
- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Changes to documentation
- **style**: Formatting, missing semi colons, etc; no code change
- **refactor**: Refactoring production code
- **test**: Adding tests, refactoring test; no production code change
- **chore**: Updating build tasks, package manager configs, etc; no production code change
### 2.2. Subject
Subject specifies the title of commit according to the rules below.
- The title does not exceed **50** characters and does not have a period.
- Write in a **command tone** without using the past tense.
- The **first letter** of the title must be **capitalized**.
- If there is an **issue**, it should be attached to the title or text.
```
feat: Summarize changes in around 50 characters or less
```
### 2.3. Body
Body specifies specific additional information according to the rules below. *Body is an option*.
- Separate the title and the body by a **blank line**.
- Do not exceed **72** characters per line.
- Write according to **what** and **why** rather than how.
- In addition to the explanation, it is also used to write the reason for commit.
### 2.4. Footer
Footer is used to create an Issue Tracker ID. *Footer is an option*.
```
Resolves: #123
See also: #456, #789
```
### 2.5. Example
```
feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
```

[▲ Top](#commit-rules)

<br>

## Reference
- [오늘도 야근 - Git 사용 규칙](https://tttsss77.tistory.com/58)
- [Udacity Git Commit Message Style Guide](https://udacity.github.io/git-styleguide/)
- [공대생의 차고 - Github, Git Commit Rule](https://underflow101.tistory.com/31)

[▲ Top](#commit-rules)

<br>

[← Go back to TIL](https://github.com/jeongyongs/til/)