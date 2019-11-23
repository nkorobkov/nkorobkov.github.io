---
layout: project

project-name: Bank 
title: Bank
github: https://github.com/nkorobkov/bank-lfmsh
date: 2016 - 2019
permalink: /projects/bank
  
slideshow:
  - url: /assets/bank/screen/one.png
    caption: Staff home page
    
  - url: /assets/bank/screen/two.png
    caption: View of student page for staff account

  - url: /assets/bank/screen/three.png
    caption: Form for Class admission
    
  - url: /assets/bank/screen/four.png
    caption: Staff "My transactions view", expanded
    
  - url: /assets/bank/screen/five.png
    caption: Staff "My transactions view", collapsed
    
  - url: /assets/bank/screen/six.png
    caption: Attendances report
    
  - url: /assets/bank/screen/seven.png
    caption: Money report
---

Bank is a huge project. It is a management system to support the virtual economy in summer camp for more than 130 users every year. 

Here is a table of content:
- toc
{:toc}

### Idea
Bank is a web app that holds individual accounts of more than 130 users with different permissions. 
It allows it's users to issue and transfer money and live within the virtual economic system in the [Summer Physical and Mathematical School (SPMS).](https://ipfran.ru/training/summer-school) 

### Features

From **Student** account students can:
- See their current balance and transaction history.
- See their attendance counters and the required number of attendance for each type of activity.
- Request to transfer money to a fellow student.
- See files from the global cloud.

**Staff** members have different permissions and can do much more:

- See balance, attendance and transaction history for any student in the camp.
- Create transactions to issue virtual currency to any student or group of students.
    - Each transaction should have one of **12 types** (e.g. Seminar, Activity-winners, Generic Help, e.t.c.) 
    - Each of the 12 types of transactions has different logic applied to it. 
    - After creation transactions could be altered, canceled or used as a template for new ones.
- Charge money from students for fines and purchases. 
- Increment students' attendance counters.
- Add files to the global cloud.
- Approve money transfers for students.
- See aggregated statistics on the current market state in the camp.
- Generate reports with detailed per-student statistics on balances and attendance. 
 
There is also a role of **Bank Manager**, who, in addition to regular staff actions, can also:
- See transaction history for each staff member. 
- Cancel transactions of other staff members.
- See an aggregate table of all transactions happen and sort it on different columns.  

From the **technical side** bank also has:

- API for  **Mobile App!**
- Scripts for automatic deployment. 
- Automatic tax charging with cron.


### Tech

<div class="image_row">
<div class="image_col-6">
<a href="https://python.org/" ><img src="{{site.url}}/assets/bank/tech/python.png" /></a>
</div>
<div class="image_col-6">
<a href="https://www.djangoproject.com/" ><img src="{{site.url}}/assets/bank/tech/django.png" /></a>
</div>
<div class="image_col-6">
<a href="https://www.nginx.com/" ><img src="{{site.url}}/assets/bank/tech/nginx.png" /></a>
</div>
<div class="image_col-6">
<a href="https://www.docker.com/" ><img src="{{site.url}}/assets/bank/tech/docker.jpeg" /></a>
</div>
<div class="image_col-6">
<a href="https://www.jquery.com/" ><img src="{{site.url}}/assets/bank/tech/jquery.png" /></a>
</div>
<div class="image_col-6">
<a href="https://www.postgresql.org/" ><img src="{{site.url}}/assets/bank/tech/postgres.png"/></a>
</div>
</div>


Bank is written in **Python** and relies deeply on **Django-Framework**.
Besides that, I also used:

- **Nginx** and **uwsgi** as a server.  
- **Docker** and **Docker Compose** for containerization and deployment.
- **JQuery** for AJAX and lazy-load of some pages.
- **Bootstrap** for frontend work. 
- **PostgreSQL** is the database.

### Data Model

Data Model for transactions can be difficult to grasp, but it provides great flexibility and tolerance to changes in economy game rules. 

Principal Data Model looks like this:   

<!---  --->
 <img src="{{site.url}}/assets/bank/transaction-pic.png"/>
 
 Here:
 - <span style="color:#09ABF6">**(A)**</span> - Is abstract classes (not a table).
 - <span style="color:#F5A623">**(S)**</span> - Static tables. Populated when app is deployed and then never changed.
 - <span style="color:#42b983">**(M)**</span> - Regular tables.
 - <span style="color: green">**(D)**</span> - Django provided User model.
 

### API

In 2018 one guy offered me to make an Android application for the student interface of Bank.
I agreed and developed the following *REST API* endpoints to serve application needs:

> **POST: /bank_api/login** -- checks user credentials and returns session.

> **GET: /bank_api/user** -- checks the session info and returns user and transactions information for the logged in user.

> **GET: /bank_api/users** -- returns basic info about all students in the system.

> **POST: /bank_api/add_transaction** -- checks validity of transaction and adds money transfer request into the DB.

Project succeeded and [Android application <i class="fa fa-fw fa-github"></i>](https://github.com/KeepItRealAlways/BankApp) functioned on SPMS session in 2018.

There is also a couple of endpoints for data exportation for external analysis. They are only available to users with a **Bank Manager** role. 

> **GET: /bank_api/money** -- returns information about all money transactions in the system.

> **GET: /bank_api/counters** -- returns information about all counter transactions in the system.


### Deployment

In 2019 I decided to automate deployment process and dockerize the application. 
Now it can be deployed with a single `docker-compose up` command. 


<!---  https://www.planttext.com/?text=dPJTJkCm48MlyLDOtkj829P2LmXHG5sG086gXUl1TeAthbsD7K12l3kJdwPnMs3P-2QPC_cSCpxASOY0iPnP5asq-XUVQ7pIo07beubQnX8r0slzyyoy65Sm5gR6pG5Xnf5aS8NL_9LjdO2S5kXBfqwzzSX_v7lL8i6ZqjWMV-uy30zssLiVeo320uHlKBQ7evFneABqCBctrF7laF7UQB2pyYcv-OwPZh04XEWHYl-nicI09CXcmcwrLWXvFXWCXwaFQI642Z52zCzjuu7QrqhMKskscCHIwUX2zmXvpfZpIdDnxaFaLq0XS5fmGd6w6kcwCEvbaPDJxo9G3ugsfxgMmQXxw_fRZp2QpwsH48rtNm7A-ydl2xv146T_wSPpOecr3SuMaTf8xm8dRiXbWNfoUzaL-x0sKe8c4utaOqf74Ado2AXLebGH4d-SeH5vETMnNsxSM5yqnKLQwk_bTzwMitR_wfIQEMVPqVAW-gNwi7f4VfXbpRZeWFlJgOIZ3xokDbgTHsfkCEkGp-iiiPsyiIuqoM3fR7bMpZij7MuYiOrkMgF9C1axraxH_-qT ---> 
 <img src="{{site.url}}/assets/bank/deployment-pic.png"/>

*More detailed information about an exact deployment and setup procedure can be found in <a href ="https://github.com/nkorobkov/lfmsh_bank"> GitHub repo <i class="fa fa-fw fa-github"></i></a> readme.*  

### Achievements and Metrics

App was successfully deployed and used on every session of Summer Physical and Mathematical School since 2016. 
During that period it:

- Was used by more than 400 students and 100 staff members.
- Processed over 10 000 individual transactions.
- Eliminated paperwork related to the economics game completely.
- Allowed SPMS to be run by smaller number of people, by eliminating bank specialist role. 
- Was mentioned in grant application that resulted in over $1500 donation to the SPMS program. 

### Screenshots

{% include slideshow.html %}