**Welcome to _JavaScript Programming for Planners & Designers_!**

# Syllabus

* **Course**: CPLN-692/MUSA-611, University of Pennsylvania
* **Location**: Meyerson Hall B2 and online
* **Schedule**: 1:45-4:45PM, Mondays
* **Instructor**:
  * Mjumbe Poe, mjumbe@design.upenn.edu
* **TA**:
  * Jingyi Li, jingyili@design.upenn.edu
* **Office Hours**:
  * Mjumbe:
    - Monday 4PM-5PM online
    - Wednesday 12AM-1PM TBD
    - Thursday 4PM-5PM online
    - [Book a time](https://calendly.com/mjumbe-upenn/office-hours)
  * Jingyi:
    - For now, Friday mornings
    - [Book a time](https://calendly.com/jingyili-ta/musa611)
* **Need help?**
  * [Slack organization](https://musa6112022.slack.com)
  * Stack Overflow is your friend!

This course is the first part of a 2-part track on building systems that display, analyze, and in some cases generate new geospatial data. The emphasis is on _building systems_. In this course you will build interactive interfaces to work with data, primarily in CSV and JSON format, in the web browser. In the second course (_Geospatial Cloud Computing & Visualization_) students will build scheduled, automated, cloud-based processes to clean, transform, and otherwise prepare data for analysis and visualization.

The courses are best together, but this first course can stand alone.

## Software
* Code Editors
  * [Visual Studio Code](https://code.visualstudio.com/)
  * [Sublime Text](https://www.sublimetext.com/)
* Terminals
  * [Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/install)
* Git Clients
  * [GitHub Desktop](https://desktop.github.com/)
  * [Sublime Merge](https://www.sublimemerge.com/)
* Node.js
  * [Node.js](https://nodejs.org/en/download/)

## Supplimentary Resources

* [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - A **highly authoritative** body of documentation on Javascript and many other web development topics.
* [Introduction to Web Mapping](http://132.72.155.230:3838/js/index.html) - A web-based text book specifically for JavaScript-based mapping. A good portion of this class will overlap with the material in this book.
* [30 Days of JavaScript](https://github.com/Asabeneh/30-Days-Of-JavaScript) - A step-by-step guide to learn JavaScript programming language in as few as 30 days.
* [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS) - A set of free online books which start from scratch and go, in-depth, into javascript concepts and best practices.
* [Eloquent Javascript](http://eloquentjavascript.net/) - This is a free book with some _advanced_ content. As you think about the application you might like to build for your final, the chapters on HTML forms, drawing with javascript, building a game, and constructing your own painting application will push further than we can in class.
* [Map-based Web Application Examples](webmap-examples.md)

There are additional resources on topics covered in the class in the _[resources/](resources/)_ folder.

## Objectives

* Gain familiarity and comfort with the JavaScript language (and, as necessary, HTML and CSS)
* Gain familiarity with "tools of the trade", such as code editors, git and GitHub, and practices such as testing and linting code
* Understand the structure of client-side web applications built in JavaScript, especially:
  * How web browsers load resources from the web
  * How web browsers respond to user interaction
* Know how to use mapping libraries like [Leaflet](https://leafletjs.com/index.html), along with some of its various plugins
* Know how to work with data in JavaScript, including understanding the limits of client-side data processing

## Course Outline

Throughout this 15 week course, you'll be learning to program applications using HTML, CSS, and Javascript. In addition to programming skills, we will stress the "tools of the trade": you will use a text editor designed for programming; your code will be turned in with git and managed through github. You will be programming in the same way and with some of the same tools as software developers in the industry.

We'd like to keep the course somewhat freeform — there are basic skills which must be touched on, but your interests will help shape the direction to a large extent. Most of your practice will come through building three projects in JavaScript, in addition to a self-directed final project that can take any topic you find interesting (so long as you use tools from our class).

This syllabus is a living document. As the course progresses, greater detail will be added to reflect the content of each week.

* Assessment Method / Grading Criteria:
  * Participation and exercises: 40%
  * Projects: 40%
  * Growth: 20%

### Exercises

* You’ll have _SHORT_ exercises to do in almost every class, at least for the first half of the semester
* Exercises will be submitted for credit via pull request on GitHub
* Most exercises will be checked automatically when you submit; you can always tweak until it works (i.e., the exercise due dates are flexible, but please don't wait until the end of the semester 🙏🏾)

### Structured projects

There will be three structured projects that everyone will take part in:

1. **The Class Dossier** -- This "mini-project" will help you get familiar with the structure of some of the types of data files we'll be working with in this class -- specifically JSON and HTML files.
2. **Philadelphia School Data Explorer** -- Build an interface for sorting and filtering through school data, and visualizing the results.
3. **Voter Canvassing Helper** -- Use Pennsylvania voter roll data to build an application for organizing a voter outreach effort.

### Final project

Your final assignment for the class will be decided through a project proposal negotiated with me. Final projects will be done in groups or independently — criteria for success will be hammered out in the final project proposal and group projects (if we have any) will be expected to engage with a wider scope and greater difficulty than individual projects. Group projects will also leverage the power of GitHub to make collaboration simpler and more transparent for grading purposes (this will make more sense once you're familiar with GitHub).

### Schedule

> Subject to change as necessary!

| Week | Date | Topic | Project |
| :--: | ---- | ----- | :-----: |
|   1  | 31 Aug | [Getting started](https://github.com/musa-611-fall-2022/week1) | [Class Dossier](https://github.com/musa-611-fall-2022/class-dossier) |
|   2  | 07 Sep | [Working with data](https://github.com/musa-611-fall-2022/week2) | ┴ |
|   3  | 14 Sep | [Designing systems](https://github.com/musa-611-fall-2022/week3) | [School Explorer](https://github.com/musa-611-fall-2022/school-explorer) |
|   4  | 21 Sep | [Asynchronous behavior #1 (Events)](https://github.com/musa-611-fall-2022/week4) | │ |
|   5  | 28 Sep | [DOM Manipulation](https://github.com/musa-611-fall-2022/week5) | │ |
|   6  | 05 Oct | [Styles and Layouts](https://github.com/musa-611-fall-2022/week6) | │ |
|   7  | 12 Oct | [Asynchronous behavior #2 (Requests)](https://github.com/musa-611-fall-2022/week7) | ┴ |
|   8  | 19 Oct | [Browser APIs](https://github.com/musa-611-fall-2022/week8) | [Voter Canvassing](https://github.com/musa-611-fall-2022/voter-canvassing) |
|   9  | 26 Oct | [3rd-party APIs](https://github.com/musa-611-fall-2022/week9) | │ |
|  10  | 02 Nov | [A11y, I18n, & L10n](https://github.com/musa-611-fall-2022/week10) | │ |
|  11  | 09 Nov | | ┴ |
|  12  | 16 Nov | | Final Project |
|      | ~~23 Nov~~ |  | │ |
|  13  | 30 Nov | | │ |
|  14  | 07 Dec | Project presentations | ┴ |
|      | 14 Dec | Overflow presentations<br>(if necessary) | |

#### Week 1 - Getting started
* Git and Github
* Code editing

#### Week 2 - Working with data
* First steps with Javascript/HTML/CSS (playing in the console)
* JavaSCript data types
* JSON
* GeoJSON

#### Week 3 - Designing systems
* Functions
* User stories and project management

#### Week 4 - Asynchronous behavior #1
* The Document Object Model (DOM)
* CSS selectors & the DOM
* Responding to interactive events

#### Week 5 - DOM Manipulation
* The Document Object Model (DOM)
* CSS selectors & the DOM

#### Week 6 - Styles and layouts
* CSS units
* Common CSS layout patterns
* Map tiles

#### Week 7 - Asynchronous behavior #2
* The JavaScript event loop
* Dynamically fetching data
* CSV data

#### Week 8 - Browser APIs
* Fetch (redux)
* Geolocation
* Local Storage

#### Week 9 - 3rd-party APIs
* APIs (using Mapbox and Firestore)

#### Week 10 - A11y, I18n, & L10n
* Accessibility
* Internationalization
* Localization

#### Weeks 11-13 - Possible directions
* Where to find spatial data
* Client-side geospatial analysis (Turf.js)
* D3
* Deck.gl
* Bootstrap
* Using the command line
* Server-side JavaScript (node.js)
* Advanced debugging
* Vector tiles

## Academic Integrity

In compliance with Penn's [Code of Academic Integrity](http://www.upenn.edu/academicintegrity/ai_codeofacademicintegrity.html), blatantly and egregiously copying another student's work will not be tolerated. However, because this course is designed to help prepare students for work in professional programming environments, *copying and pasting is not universally prohibited*: we encourage students to work together and to freely use the internet as a resource for finding solutions to vexing problems. Citing every copied and pasted line of code is *not* necessary. Large patterns or multiple lines of code taken from external sources *should*, however, be noted with in-code comments. If an instance is unclear, you should feel free to speak with the instructors.
