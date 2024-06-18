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

Will try to get the pieces of information related to the table such as ```table_name``` will inject ``` ' union select table_name,null from information_schema.tables#```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/8873e7af-956d-444e-b57d-639da8e436cc)

We can notice that we have many table names and one of the table names is ```users```There is a potential chance that table ```users``` must contain some credentials, Now we will go through the column name because through column name we can get the columns at which the credentials are store so the payload looks like this ```' union select column_name,null from information_schema.columns from table_name='users'```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/6135d1b9-4163-4c2f-9a32-9fa6acebd729)

We can observe from above that columns name such as ```id,login,password``` have high chances of containing credentials so will be using the final payload to get all the details ```'UNION select user,password from users#```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/b80fbf82-7fae-4b8c-b1a3-ac0ed991b28c)

We have found out the username and password of many users 

# SQL (Medium)

We have the final payload ``` Union select user,password from users#``` this will work on both the level ```medium``` and ```hard``` we just need to find the injected parameter this level will be performed with the help of ```Burp Suite```

First Intercept the request 

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/649efa19-e910-4917-9192-303da6f1eac7)

We will be using the ```id``` parameter to inject SQLi the payload will be the same i.e ```1 UNION select user,password from users#```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/ef0a9b27-069b-4f5e-990b-cd765424fa2b)

Now click on forward we can observe that we have all the credentials 

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/d9f4657a-17fe-453d-9ec2-38bc5acc1e72)

# SQL (Hard)

We have the final payload ``` Union select user,password from users#```This will work on both the levels ```medium``` and ```hard``` we just need to find the injected parameter this level will be performed with the help of ```Burp Suite```

Click on ```here to change the id```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/f140ec91-5604-4903-a8cf-00ca950ecb72)

after clicking a different prompt will appear 

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/39a191f6-6ae0-421b-a91e-e2bb46d3dc3c)

Try to insert the same payload i.e ``` ' Union Select user,password from users# ```

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/704d0d77-b194-4fa3-8c78-74c7bd8fb911)

Click on ```submit``` and check out the first prompt all the user credentials are displayed

![image](https://github.com/kashrathod19/SQL-Injection-DVWA-SOLUTION/assets/54115061/4e1209cb-0699-4b92-a450-aa077a3f174d)



