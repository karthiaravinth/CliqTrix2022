# CliqTrix 2022 Competition Hotel Management - Django 

#### The Hotel Management System has 5 different user types(each has different functions) : <br>
 Admin , Manager , Receptionist , Staff and Guest
## Admin 

![](/ScreenShots/Booking%20Confirmation%20Admin.png)

## Manager 

![](/ScreenShots/Add%20Employees.png)

## Receptionist 

![](/ScreenShots/Events%20Page%20Admin.png)

## Staff 

![](/ScreenShots/Login%20Page.png)

## Guest

![](/ScreenShots/Book%20&%20Add%20People.png)

### In order to download and run the project (Needs Python 3 ):
1. Install Pythpn and Django :
```shell
pip install Django
pip install django-phonenumber-field[phonenumbers]
```
## Needed to create roles and admin account to add new employee accounts
2. Change the directory to CliqTrix2022 and start the Shell:
```shell
python3 manage.py shell
```
* Then execute these, one by one:(for creating the Admin Access)
```shell
from django.contrib.auth.models import Group, User
```

```shell
from accounts.models import Employee
```

```shell
Group.objects.create(name='admin')
```

```shell
Group.objects.create(name='manager')
```

```shell
Group.objects.create(name='receptionist')
```

```shell
Group.objects.create(name='staff')
```

```shell
Group.objects.create(name='guest')
```

```shell
user = User.createuser=User.objects.create_user('admin', password='admin123')
```

```shell
group = Group.objects.get(name="admin")
```

```shell
user.groups.add(group)
```

```shell
admin = Employee(user=user, salary=0)
```

```shell
admin.save()
```

### Finally:
* Exit the shell and set the database: 
```shell
python3 manage.py makemigrations
python3 manage.py migrate
```
* Then, start the server
```shell
python3 manage.py runserver
```
Now Works it. Copy and paste the IP address in browser

## Notes:
#### Note 1: In the program, there are some payment page. No need to enter real credit-card informations. 

#### Note 2: You can only sign up as a guest to the system. 

#### Note 3: In order to add new employee (Manager - Receptionist - Staff): 
* Login in to the system with username: "admin" and password : "admin123"
* Go the employee page and Click "Add New Employee" button, fill the form.

#### Note 4: For the email system (In some cases system sends e-mails):
* Go to the CliqTrix2022/setting.py
* In Email Variable change it to your mail
