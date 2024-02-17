# WAPH-Web Application Programming and Hacking
## Instructor: Dr. Phu Phung

# Individual Project 1
## Front-end Web Development with a Professional Profile Website on github.io cloud service

## Overview

In this project,we expanded the front-end web development skills by developing a Professional Profile Website and deploying it on `github.io` cloud service. We have worked with CSS frameworks like Bootstrap and also java script frame works like Jquery and React .You can find all the code and files realted to this project here .

[https://github.com/vemanava77/vemanava77.github.io](https://github.com/vemanava77/vemanava77.github.io)

### General requirements :

Let's start from the first as you can seen in the Navbar and Details image you will find Navbar which will help you navigate you to differnet sections of  the webpage and it stays on the top even if you scoll down making the navigation easy . Below the navigtaion  you can see the personal Details and Headshot Image .The Githu  and Linked takes you to the those profiles . As you can see a message below Welcome to my home Page . This is enabled by cookies i.e when you visit the for the first time you get Welcome message but if you are a old user then you will see a welcome back message . And the Page is completly mobile responsive as you can see below.


![Navbar and Details ](images/1.png)


![Navbar and Details responsive view  ](images/2.png)


![Navbar and Details responsive view  ](images/3.png)


Lets see how we were able to achieve these first we need to link bootstrap CDN so that we can use those classes
which can be achived by add the below lines of code to our head tag in index.html file

```
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" 
    rel="stylesheet"
    integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" 
    crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
    crossorigin="anonymous"></script>
```

Now lets see how can we achieve the navbar 


```
<nav class="navbar navbar-expand-lg navbar-light bg-light sticky-top">
            <div class="container">
                <a class="navbar-brand" href="#">Vemana</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" 
                data-bs-target="#navbarNav"
                    aria-controls="navbarNav" aria-expanded="false" 
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav ms-auto">
                        <li class="nav-item">
                            <a class="nav-link" href="#about">About</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#Education">Education</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#Experience">Experience</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#projects">Projects</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="#contact">Contact</a>
                        </li>
                    </ul>
                </div>
            </div>
</nav>
```


the below code help to acheive details section


```
<section class="container py-5">
            <div class="row align-items-center">
                <div class="col-12 col-md-4">
                    <img src="images/dispaly_pic.jpeg" alt="Headshot" 
                    class="img-fluid rounded-circle">
                </div>
                <div class="col-12 col-md-7">
                    <h1>Vijay Kumar Vemana</h1>
                    <p><a href="mailto:youremail@example.com">vemanava@mail.uc.edu</a></p>
                    <p><strong>(513) 413-8621</strong></p>
                    <p><a href="https://www.linkedin.com/in/vijaykumarvemana/">LinkedIn</a></p>
                    <p><a href="https://github.com/vemanava77">GitHub</a></p>
                    <p><a href="files/Resume.pdf" class="btn btn-primary"
                            download="VijayKumarVemana_Resume.pdf">Download Resume</a></p>
                </div>
            </div> 
</section>
```

And lets add a few custom styles along with the Bootstrap 


```
body {
            background-color: #e5f0f2;
        }
```


In order to achieve the welcome and welcome back messaage we need to create a cookie and then we can use it 


```
<section>   
        <!-- Cookie and Message-->
    <div class="container py-3">
        <div id="last-visit" class="alert" role="alert">
        </div>
    </div>
    <!-- Cookie-->
    <script>
        // Function to set a cookie
        function setCookie(cname, cvalue, exdays) {
            const d = new Date();
            d.setTime(d.getTime() + (exdays * 24 * 60 * 60 * 1000));
            let expires = "expires=" + d.toUTCString(); 
            document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
            
        }

        // Function to get a cookie
        function getCookie(cname) {
            let name = cname + "=";
            let decodedCookie = decodeURIComponent(document.cookie);
            let ca = decodedCookie.split(';');
            for (let i = 0; i < ca.length; i++) {
                let c = ca[i];
                while (c.charAt(0) === ' ') {
                    c = c.substring(1);
                }
                if (c.indexOf(name) === 0) {
                    return c.substring(name.length, c.length);
                }
            }
            return "";
        }

        function checkCookie() {
            let lastVisit = getCookie("lastvisit");
            let message = document.getElementById('last-visit');
            if (lastVisit !== "") {
                message.className += " alert-info";
                message.innerHTML = `Welcome back! Your last visit was on ${lastVisit}.`;
            } else {
                message.className += " alert-success";
                message.innerHTML = "Welcome to my homepage!";
            }
            setCookie("lastvisit", new Date().toLocaleString(), 365);
        }
    </script>
</section>
```



+ Create a link to a new HTML page to introduce this "Web Application Programming and Hacking" course and related hands-on projects (5 pts)
 ​
### Non-technical requirements (20 pts)​

+ Use an open-source CSS template or framework such as Bootstrap​

_Target this profile for your potential employer, and your page will be graded as a part of your job application​_

+ Include a page tracker, for example: [https://analytics](https://analytics.withgoogle.com/)](https://analytics.withgoogle.com/), [https://flagcounter.com/](https://flagcounter.com/).

### Technical requirements (50 pts)​

#### Basic JavaScript code (20 pts)​

+ Use jQuery and one more open-source JavaScript framework/library​ to implement JavaScript code introduced in Lab 2, including, a digital clock; an analog clock; show/hide your email; and one more functionality of your choice. **(5 pts each)**

+ Two public Web APIs integration (20 pts)​

1. Integrate the jokeAPI ([https://v2.jokeapi.dev/joke/Any](https://v2.jokeapi.dev/joke/Any), similar to Lab 2.2.d.i) with Any category of joke to display a new joke in your page every 1 minute

2. Integrate a public API with graphics. Examples: [https://xkcd.com/info.0.json](https://xkcd.com/info.0.json), [https://www.weatherbit.io](https://www.weatherbit.io).

+ Use JavaScript cookies to remember the client (10 pts): If first-time visit, display a message "Welcome to my homepage!", otherwise, display a message "Welcome back! Your last visit was <the date/time of last visit>"


## Report

You can write a report using Markdown format or any Word processor, i.e., you do not need to use Markdown to write your report. Your report should follow the template/outline provided in Lecture 2 ([https://github.com/phungph-uc/waph/blob/main/README-template.md](https://github.com/phungph-uc/waph/blob/main/README-template.md)) which should include the course name and instructor, your name and email together with your headshot (150x150 pixels), and sub-sections of the assignment's overview, and each task and sub-task.

There should be an overview sub-section where you must write an overview of the assignment and the outcomes you learned from it. Include your website's clickable URL deployed on `github.io`. Also, include a direct clickable link to the project folder on GitHub.com so that it can be viewed when grading, for example, [https://github.com/phungph-uc/waph-phungph/tree/main/individual-project1](https://github.com/phungph-uc/waph-phungph/tree/main/individual-project1).

For each sub-task, write a brief summary of how you complete it. You are welcome to include code snippets and screenshots to demonstrate the outcome, however, they are not required. **Please note that demo screenshots must include your virtual machine name or your name with proper captions and be visible, i.e., in high resolution, not too blurry or with much blank space, for grading**. 

Your report must be exported in  PDF with contents and screenshots are correctly rendered in proper order. The PDF file should be named `your-username-waph-project1.pdf`, e.g., `phungph-waph-project1.pdf`, and uploaded to Canvas to submit by the deadline. 


## Deliverables and Submission

You need to submit **three** deliverables in PDF files for grading:

+ Your report mentioned above.

+ Your deployed website printed from a browser in PDF.

+  The source code of your deployed website printed from a browser in PDF.