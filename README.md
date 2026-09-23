# B.Tech CSE Question Bank Website

A pure HTML-based B.Tech CSE Question Bank website created as part of
the Web Technology assignment.

The project demonstrates basic HTML elements, forms, tables, lists,
frames, multimedia, HTML5 native validation, and the `<details>` /
`<summary>` interactive elements.

> **Technology used:** HTML5 only\
> **JavaScript:** Not used\
> **CSS:** Not required for the assignment\
> **Backend/Database:** Not used

------------------------------------------------------------------------

## 1. Project Objective

The objective of this assignment is to create a small multi-page
Question Bank website where:

1.  A student first fills in a registration form.
2.  After registration, the student enters the Question Bank home page.
3.  The home page is divided into frames.
4.  The left frame contains the semester-wise course structure.
5.  Subjects can be expanded/collapsed using native HTML5 `<details>`
    and `<summary>`.
6.  A subject's question paper can be opened in the right frame.
7.  A Student Feedback/Blog page contains student comments, images and a
    video.
8.  The feedback page also contains a form for adding a new comment,
    image and video.
9.  HTML5 validation features are used in the registration form.

------------------------------------------------------------------------

# 2. Project Structure

The project can be arranged as follows:

``` text
Assign01/
│
├── registration.html
├── home.html
├── header.html
├── menu.html
├── welcome.html
│
├── computing.html
├── program_C.html
├── dsa.html
├── dbms.html
├── os.html
│
├── blog.html
│
├── images/
│   ├── friend1.jpg
│   ├── friend2.jpg
│   └── friend3.jpg
│
└── videos/
    └── review.mp4
```

If additional subjects or files are added, they can be placed in the
same `Assign01` directory.

------------------------------------------------------------------------

# 3. How to Run the Project on a Laptop

## Method 1: Open directly in a browser

No server is required for basic testing.

1.  Download or clone the repository.
2.  Open the project folder.
3.  Open `registration.html` in Google Chrome, Microsoft Edge, or
    another modern browser.
4.  Fill in the registration form.
5.  Click **Register**.
6.  The `home.html` page will open.

Because the project uses relative paths, all HTML files and folders
should retain their original structure.

------------------------------------------------------------------------

## Method 2: Using VS Code

1.  Install Visual Studio Code.
2.  Open the project folder in VS Code.
3.  Open `registration.html`.
4.  Right-click the file.
5.  Select **Open with Live Server** if the Live Server extension is
    installed.

Alternatively, the HTML file can simply be opened directly in a browser.

------------------------------------------------------------------------

# 4. Running It on a Linux Apache Lab Server

The college lab uses Apache's `UserDir` setup.

The important directory is:

``` text
/home/<username>/public_html/
```

The project is placed inside:

``` text
/home/<username>/public_html/Assign01/
```

For example:

``` text
/home/arpans/public_html/Assign01/
```

The `public_html` directory is used because Apache is configured to
serve the user's public web files through the `~username` URL.

------------------------------------------------------------------------

## 4.1 Create the project directory

From the terminal:

``` bash
cd ~
mkdir -p public_html/Assign01
```

Move/copy all project files into:

``` text
~/public_html/Assign01/
```

------------------------------------------------------------------------

## 4.2 Check the files

Run:

``` bash
cd ~/public_html/Assign01
ls
```

You should see files such as:

``` text
registration.html
home.html
header.html
menu.html
welcome.html
computing.html
program_C.html
dsa.html
dbms.html
os.html
blog.html
```

and the `images` and `videos` directories.

------------------------------------------------------------------------

## 4.3 Set permissions if required by the lab server

If the college server requires the files to be readable by Apache:

``` bash
chmod -R 777 ~/public_html/Assign01
```

### Meaning of `777`

``` text
7 = read + write + execute
```

So:

``` text
777
```

gives read, write and execute permissions to:

-   Owner
-   Group
-   Others

> `777` is used here only because it may be required/accepted in the
> college lab environment. It is not recommended for normal production
> web servers.

A production server would normally use more restrictive permissions.

------------------------------------------------------------------------

# 5. Opening the Website Through the College IP

Suppose the professor provides an IP address:

``` text
192.168.10.25
```

and the Linux username is:

``` text
arpans
```

Because the project is inside `Assign01`, the URL is:

``` text
http://192.168.10.25/~arpans/Assign01/registration.html
```

The mapping is:

``` text
http://IP/~username/
        ↓
/home/username/public_html/
        ↓
Assign01/
        ↓
registration.html
```

Therefore:

``` text
http://IP/~username/Assign01/registration.html
```

corresponds to:

``` text
/home/username/public_html/Assign01/registration.html
```

------------------------------------------------------------------------

# 6. Registration Page

File:

``` text
registration.html
```

This is the first page of the website.

The user enters:

-   Name
-   Roll Number
-   Registration Number
-   Department
-   Semester
-   Gender
-   Date of Birth
-   Mobile Number
-   Email
-   Address
-   Photograph

The form contains:

``` html
<form action="home.html">
```

Therefore, after successful HTML validation and clicking **Register**,
the browser navigates to:

``` text
home.html
```

No JavaScript is required.

------------------------------------------------------------------------

# 7. HTML5 Validation Used in Registration

The registration form demonstrates several native HTML5 validation
features.

## Required fields

Example:

``` html
<input type="text" required>
```

The browser does not allow the form to be submitted until the required
field is filled.

------------------------------------------------------------------------

## Roll Number Pattern

The roll number uses:

``` html
pattern="[A-Z]{2}[0-9]{4}"
```

This accepts a format such as:

``` text
CS2026
IT1234
EC2025
```

The pattern means:

``` text
[A-Z]{2}   → exactly two uppercase letters
[0-9]{4}   → exactly four digits
```

A custom explanation is provided using:

``` html
title="Roll Number should be in the format CS2026."
```

------------------------------------------------------------------------

## Name Pattern

The name uses:

``` html
pattern="[A-Za-z ]+"
```

This allows alphabets and spaces.

------------------------------------------------------------------------

## Mobile Number Pattern

The mobile number uses:

``` html
pattern="[0-9]{10}"
```

This requires exactly 10 digits.

------------------------------------------------------------------------

## Email Validation

The email field uses:

``` html
<input type="email">
```

The browser performs basic email-format validation automatically.

------------------------------------------------------------------------

## Date Range

The Date of Birth field uses:

``` html
<input
    type="date"
    min="2000-01-01"
    max="2010-12-31"
>
```

This restricts the selectable date range.

------------------------------------------------------------------------

# 8. Department Auto-Complete

The department field demonstrates the HTML5 `<datalist>` element.

Example:

``` html
<input
    type="text"
    list="departmentList"
>
```

The suggestions are defined by:

``` html
<datalist id="departmentList">
    <option value="Computer Science & Engineering">
    <option value="Information Technology">
    <option value="Electrical Engineering">
    <option value="Mechanical Engineering">
    <option value="Civil Engineering">
</datalist>
```

As the user types, the browser provides matching suggestions.

This functionality is completely native to HTML5.

------------------------------------------------------------------------

# 9. Home Page and Frames

File:

``` text
home.html
```

The home page uses the traditional HTML `<frameset>` structure required
for the assignment.

The layout is:

``` text
+---------------------------------------------+
|                  HEADER                     |
+-------------------+-------------------------+
|                   |                         |
|      MENU         |       CONTENT           |
|                   |                         |
|                   |                         |
+-------------------+-------------------------+
```

The main structure is:

``` html
<frameset rows="15%,85%">

    <frame src="header.html" name="header">

    <frameset cols="30%,70%">

        <frame src="menu.html" name="menu">

        <frame src="welcome.html" name="content">

    </frameset>

</frameset>
```

------------------------------------------------------------------------

# 10. How the Frames Work

The important part is:

``` html
<frame src="welcome.html" name="content">
```

This creates the right-side frame and gives it the name:

``` text
content
```

The links in `menu.html` use:

``` html
target="content"
```

For example:

``` html
<a href="dbms.html" target="content">
    Open Question Paper
</a>
```

When the link is clicked, `dbms.html` opens **inside the frame named
`content`**.

The header and menu remain unchanged.

------------------------------------------------------------------------

# 11. Menu and Semester-wise Course Structure

File:

``` text
menu.html
```

The menu contains a semester-wise nested list using:

``` html
<ul>
<li>
```

The structure is approximately:

``` text
Semester 1
    ├── Introduction to Computing
    ├── Mathematics-I
    └── Physics

Semester 2
    ├── Programming in C
    ├── Mathematics-II
    └── Electrical Engineering

Semester 3
    ├── Data Structures
    ├── Database Management System
    └── Digital Electronics

Semester 4
    ├── Operating System
    └── Computer Networks
```

------------------------------------------------------------------------

# 12. Bonus Task 1: Interactive Collapsible Syllabus

The bonus assignment adds native HTML5 interaction using:

``` html
<details>
```

and:

``` html
<summary>
```

Example:

``` html
<details>

    <summary>Database Management System</summary>

    <p><b>Course Credits:</b> 4</p>

    <ul>
        <li>Introduction to DBMS</li>
        <li>ER Model</li>
        <li>Relational Model</li>
        <li>SQL</li>
        <li>Normalization</li>
    </ul>

    <a href="dbms.html" target="content">
        Open Question Paper
    </a>

</details>
```

The `<summary>` acts as the clickable heading.

Clicking it expands or collapses the syllabus.

No JavaScript is used.

------------------------------------------------------------------------

# 13. Question Paper Pages

The project contains individual question paper pages such as:

``` text
computing.html
program_C.html
dsa.html
dbms.html
os.html
```

Each page contains an online question paper form with elements such as:

-   Student name
-   Roll number
-   Multiple-choice questions
-   Radio buttons
-   Checkboxes
-   Textarea
-   Submit button
-   Reset button
-   Link back to the main page

The pages can be opened inside the right-side `content` frame.

------------------------------------------------------------------------

# 14. Student Feedback / Blog

File:

``` text
blog.html
```

The Student Feedback page contains:

1.  Student opinion video
2.  Student comments
3.  Student photographs
4.  Add Your Comment form

------------------------------------------------------------------------

## Student Opinion Video

The page uses the HTML5 `<video>` element.

Example:

``` html
<video width="500" controls>
    <source src="videos/review.mp4" type="video/mp4">
</video>
```

The video is stored in:

``` text
videos/review.mp4
```

The `controls` attribute provides the browser's built-in video controls.

------------------------------------------------------------------------

# 15. Student Comments

Student feedback is displayed using an HTML table.

The table contains information such as:

``` text
Photo | Name | Comment
```

Images are stored inside:

``` text
images/
```

For example:

``` text
images/friend1.jpg
images/friend2.jpg
images/friend3.jpg
```

------------------------------------------------------------------------

# 16. Add Your Comment Form

The feedback page also contains an HTML form for adding a new comment.

It includes:

-   Name
-   Email
-   Profile photo upload
-   Opinion video upload
-   Comment
-   Post Comment button
-   Clear button

Example:

``` html
<input type="file" name="photo" accept="image/*">
```

and:

``` html
<input type="file" name="video" accept="video/*">
```

The `accept` attribute helps the browser filter the file selection.

------------------------------------------------------------------------

## Important limitation

This project uses HTML only.

Therefore, the **Post Comment** button does not actually save a new
comment to a database or dynamically add it to the page.

To make the feature fully functional, a backend such as PHP/Node.js and
a database would be required.

The form is included to demonstrate the required HTML interface.

------------------------------------------------------------------------

# 17. Important HTML Concepts Demonstrated

This project demonstrates:

### Basic HTML

-   `<html>`
-   `<head>`
-   `<title>`
-   `<body>`
-   `<h1>` to `<h3>`
-   `<p>`
-   `<hr>`
-   `<br>`

### Lists

-   `<ul>`
-   `<ol>`
-   `<li>`

### Links

-   `<a>`
-   `href`
-   `target`

### Tables

-   `<table>`
-   `<tr>`
-   `<td>`
-   `<th>`

### Forms

-   `<form>`
-   `<input>`
-   `<textarea>`
-   `<select>`
-   `<option>`
-   `<button>` / submit and reset inputs

### HTML5 Input Types

-   `text`
-   `email`
-   `tel`
-   `date`
-   `file`

### HTML5 Validation

-   `required`
-   `pattern`
-   `min`
-   `max`
-   `placeholder`
-   `title`
-   `accept`

### HTML5 Interactive Elements

-   `<details>`
-   `<summary>`
-   `<datalist>`

### Multimedia

-   `<img>`
-   `<video>`
-   `<source>`

### Frames

-   `<frameset>`
-   `<frame>`

------------------------------------------------------------------------

# 18. Complete User Flow

The complete flow of the website is:

``` text
                    START
                      |
                      v
              registration.html
                      |
                      |
              Fill registration form
                      |
                      v
             HTML5 validation
                      |
                 Valid?
                /     \
              No       Yes
              |         |
              |         v
              |      home.html
              |         |
              |         v
              |   +-------------+
              |   |   Header    |
              |   +-------------+
              |   | Menu |     |
              |   |      |     |
              |   |      |Content
              |   +------+-----+
              |         |
              |         v
              |    Select Semester
              |         |
              |         v
              |    Expand Subject
              |         |
              |         v
              |  Open Question Paper
              |         |
              |         v
              |  Question paper opens
              |  inside content frame
              |
              |
              +---- validation error
```

The Student Feedback page can also be opened from the menu:

``` text
home.html
    |
    v
Student Feedback
    |
    +--> Opinion Video
    |
    +--> Student Comments
    |
    +--> Add Your Comment
```

------------------------------------------------------------------------

# 19. GitHub Setup

The project can be uploaded to GitHub with the complete folder
structure.

Example:

``` bash
git init
git add .
git commit -m "Add Web Technology HTML assignment"
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

After cloning the repository on another computer, keep the same folder
structure and open:

``` text
registration.html
```

The project should work without installing any programming language or
database.

------------------------------------------------------------------------

# 20. Notes for Reproducing the Assignment

To reproduce the assignment exactly:

1.  Clone/download the repository.
2.  Keep all HTML files in the same project directory.
3.  Keep the `images` folder inside the project.
4.  Keep the `videos` folder inside the project.
5.  Open `registration.html`.
6.  Complete the registration form.
7.  Click **Register**.
8.  Explore the frameset-based Question Bank.
9.  Expand semesters and subjects using the native HTML controls.
10. Open the available question papers.
11. Open the Student Feedback page.
12. Play the sample opinion video.
13. Test the Add Your Comment form.
14. Test invalid registration values to observe HTML5 validation.

For the college Linux server, place the project under:

``` text
~/public_html/Assign01/
```

and access it using:

``` text
http://<IP>/~<username>/Assign01/registration.html
```

------------------------------------------------------------------------

# 21. Conclusion

This project implements the complete HTML Question Bank assignment and
its bonus tasks using native HTML/HTML5 features.

The main concepts demonstrated are:

``` text
HTML
 ├── Forms
 ├── Tables
 ├── Lists
 ├── Links
 ├── Images
 ├── Video
 ├── Frames
 ├── HTML5 Validation
 │    ├── required
 │    ├── pattern
 │    ├── min / max
 │    ├── type
 │    └── accept
 ├── datalist
 └── details / summary
```

The project intentionally avoids JavaScript and backend technologies so
that the native HTML5 features required by the assignment can be clearly
demonstrated.
