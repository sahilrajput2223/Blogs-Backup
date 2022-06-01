## Python Django :: Let's Do It

Hello World !

During this time, everyone wants to learn about python programming language, because python can be used in many section like web-development, Internet of things, networking, data science, machine learning, deep learning and AI.

In this blog, we will see how to develop basic Contact Directory web-app using Python-Django. 

Before that, make sure you have installed python in your system. to download and install python in your system you can follow this  [link](https://www.python.org/) .

Once you have python installed in your system you can follow along with this blog to develop Contact Directory web-app.

We are going to use Virtual Environment concept here, so for that we need to install python virtual environment first.

To install python virtual environment, we need to enter `pip install virtualenv` this command in cmd.

After that we can create virtual environment for particular projects. for that we are going to use `virtualenv ContactDirectoryEnv` command. it will create ContactDirectoryEnv named virtual environment.


Now, to activate that virtual environment we need to run activate.bat file which is located on `/ContactDirectoryEnv/Scripts/activate` path. After that virtual environment is activated and we are good to go to install django in virtual environment.

To install latest version of Django, we need to run `python install django` command. it will  collect related packages and install django in virtual environment.

To verify it's installed or not, we can use `pip list` command. we can see the version and packages details as displayed in below mention image.
![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616131138929/k9_AVjUON.png)

Now, we need to create Python-Django project. For that we have to use `django-admin startproject ContactDirectory` command. here, `ContactDirectory` is project name.

Till here, our basic project structure is created. Now we need to open this folder(project structure) in any IDE you like(I'm using PyCharm). In that IDE, you have to set project specific python interpreter as `/ContactDirectoryEnv/Scripts/python.exe`.

Now, we need to make this changes to database also. We are using sqlite3 database here.
For that we need to use `python manage.py makemigrations` and `python manage.py migrate` command.

With the help of `python manage.py makemigrations` command we will generate migrations which we need to apply on database and with the help of `python manage.py migrate` we will apply that migrations on database.  

Once, all migrations applied successfully on database, we can see the following screen. 

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616132543638/iE06tTBMX.png)

Now, to run this python-django app we need to use `python manage.py runserver` command.
And, if everything goes right and app is started, then we can see below mention messages in cmd.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616132715633/3ct__hOnG.png)

Now, in cmd we can see one link like (http://127.0.0.1:8000). using this link we can open our app in browser also. Once we hit that link, we can see below mention screen as result.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616132895493/noCsAnpix.png)

Great, till now you have successfully started your python-django app. now further we are going to make changes in this app according to our Contact Directory web-app. 

**Take a little break and give yourself a cheer.**

Once you open that project in any IDE, you can see there is some files like, settings, manage, urls and so on.

First of all, we will start editing settings file.

In settings file, there is one key named `TIME_ZONE`. we need to set that value as `TIME_ZONE ='Asia/kolkata'`. So, our app will use our timezone.

Now, we need to create one app in which we are going to add our database, front-end, views and other urls related logic. for that we need to use `python manage.py startapp Home`. Here, `Home` is our app-name. 

After this, app named `Home` is created in that project structure. But we need to mention this newly created app in `INSTALLED_APPS` key in settings file so that our web-app knows that there is one app called `Home` created in this project. It will looks like below mention image.


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616134282727/G9CLsA4M2.png)
   
Now, we need to create one `Templates` folder in which we are going to add our html related codes. Also we need to mention this folder in settings file also (as displayed in below mention image).

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616134796380/oYhFt1_02.png)
 

Now, we are going to do some changes in models file, which is located in Home app.

In this file, we are going to add our database related logics like how we want to create out database tables and which types of column we are going to use. Add code in models file as displayed in below image.


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616136027450/aHVMdkg5l.png)

Here, we are using five columns in database table to save contact details.

- Name: name column is used to add contact person name (having max value length 50 and unique value)
- Email: email column is used to add contact person email (having unique value)
- Contact Number: contactNumber is used to add contact number of person (having max value length 10 and unique value) 
- Created At: used to store information as on which date data is created.
- Updated At: used to store information as on which date data is last modified.

Now, we need to create new forms file in Home app, as we are going to use forms file with views, and urls file to generate out html page.

To generate html from models file, we are going to use `django-crispy-forms`. We need to run `pip install django-crispy-forms` to install crispy forms in our python-django project.Also we have to mention `crispy_forms` tag in `INSTALLED_APPS` section of settings file. 

Now, in forms file we need to add below mention code to generate forms form our database model.


![forms.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616139638841/5e2GU7J0Y.png)
- In forms file, we are mentioning our model using `model = 'model_name'` for which we want to create form.
- Also, we are adding that we want to use all fields from that model using `fields='__all__'` logic.
 
Now, we need to add below mention logic in views file for our forms so that we can link our html page with database(models and forms) file logic.


![views.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616139763499/w5Cna17rg.png)

- In views file, we will check if the request is `POST` then we will validate that data and add that data in database.
- Also, if the request is not `POST` then empty form will generated and passed to addDetails(html page) page using `crispy forms` runtime render logic.

Now, we have to create urls related file (named: urls_home) in Home app. This file is used to create url redirection logic in Home app.

In urls_home, we need to mention below mention logic to make url redirection logic.

![urls.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616141620354/dbd2NMnA7.png)

Now, we need to mention this urls_home file from Home app in main urls file which is available in main structure (ContactDirectory/urls) as displayed in below mention image.


![urls.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616141886095/_UQ5_OU_U.png)

 
Now, we need to make migrations and apply that migrations to database so that created model in models file is created in database.

So, let's apply `python manage.py makemigrations` and then `python manage.py migrate` command.

Once, all migrations applied successfully on database will see messages as mention in below image. 


![model.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616142067421/XepgQVWvd.png)
  

Now, let's run this using `python manage.py runserver` command.

Once web-app is started, we have to open `http://127.0.0.1:8000/Home/AddDetails` url so that we can see add details related page(as displayed in image)


![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616142298871/d3Wbn3Wvi.png)

 - here, `http://127.0.0.1:8000` is our base-path, then `Home` is our app related path and at last `AddDetails` is our html related path.

- and, if we add details here and click on `Add` button then it will add that data in database.

At database side, data is added like displayed in below mention image.


![db.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1616142742928/a9dcd7Quy.png)


Here, to open database file we need to use some database tool (I'm using  [sqlitebrowser](https://sqlitebrowser.org/)).

Django Official Documentation  [link](https://docs.djangoproject.com/en/3.1/) . 

we have seen,

- How to install and add Virtual Environment in system.
- How to activate Virtual Environment.
- How to install Django and crispy_forms in Virtual Environment.
- How to create basic app and run it, after applying all the migrations.
- How to create internal app and create models, views, forms and html related files.
- Also, how to add data in database using crispy forms logic.


Thank you for reading, You can connect me on  [Twitter](https://twitter.com/Its_SR__)   /  [LinkedIn ](https://www.linkedin.com/in/rajputsahil/) /  [Github ](https://github.com/sahilrajput2223) .