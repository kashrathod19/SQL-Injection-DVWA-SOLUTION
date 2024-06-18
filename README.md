# SQL-Injection-DVWA-SOLUTION
The Damn Vulnerable Web Application (DVWA) is a popular web application designed to help security professionals and enthusiasts practice their skills in a legal and controlled environment. This repository specifically focuses on SQL Injection vulnerabilities, providing detailed explanations and step-by-step solutions for each challenge level.

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/280c20dd-f03c-4805-b139-2104a93e470a)

Welcome to the repository containing comprehensive solutions for SQL Injection vulnerabilities in the Damn Vulnerable Web Application (DVWA). This repository is curated and maintained by Nihar Rathod, also known as Bugbot19, a seasoned security researcher and ethical hacker.

Repository Contents

Low-Level Solutions: Detailed walkthroughs for exploiting SQL Injection vulnerabilities at the 'Low' security level of DVWA. These solutions demonstrate basic techniques and concepts for beginners.

Medium-Level Solutions: Comprehensive solutions for the 'Medium' security level, showcasing intermediate techniques and methods to bypass slightly more complex protections.

High-Level Solutions: Advanced SQL Injection techniques and solutions for the 'High' security level, aimed at overcoming sophisticated security mechanisms.

# SQL (LOW)

First, we try to understand the working by inserting ```1``` in the textbox

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/f5cf6cdf-6b73-4fc3-8143-cf2cd53fd895)

We can observe that it had given us the detail of user-id ```1```

Now, we will try to get all the details of users by using a simple but effective payload i.e ```' or 1=1#```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/21939e1a-d841-4e1f-a21d-7d4eaf1180a3)
