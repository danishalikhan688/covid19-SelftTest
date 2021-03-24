# Self_Test
                                For running on local system 
step 1 : 
open terminal run command 

npm install 

step 2

npm start




                                    For running on heroku server
step 1 : 

create a repository in github and clone the folder where your code is place

step 2

create a Procfile in your root directory where server.js is place and paste the following line 

web: npm install && node server.js

step 3

change the port in server.js line no 5 -> 3000 to 80


step 4

open the terminal and run the following commands 

-> git add .
-> git commit -m "Added a Procfile."
-> heroku login
-> Enter your Heroku credentials.
...
heroku create [your-app-Name]

 this command will provide you 2 links e.g
Creating arcane-lowlands-8408... done, stack is cedar
http://arcane-lowlands-8408.herokuapp.com/ | git@heroku.com:arcane-lowlands-8408.git
 
git push heroku main
...

after successfull push console will give you your deployed app link



Appendix: 


1 : Your port must be dynamic e.g  const PORT = process.env.PORT || 80;

2 : If still not working than run the below command

->  rm yarn.lock
->  git commit -am "Remove yarn lock file"
-> git push heroku main

3 : If it through error : your repository is not located
Example: 
remote: !       No such app as salty-taiga-84495.
fatal: repository 'https://git.heroku.com/salty-taiga-84495.git/' not found
 
than run the following command to change the git repository directory

-> git remote rm heroku
-> git remote add heroku e.g [your repository linke which terminal gave you above]
Example : 
git remote add heroku https://git.heroku.com/app-name.git
  4 : If your terminal through error in or not support “git” and heroku” than download CLI for git and heroku and set the path for both:
Heroku : 
https://devcenter.heroku.com/articles/heroku-cli
Git: 
https://git-scm.com/downloads
