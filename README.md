# REVcalc

### Capital tax and profit calculator from stock investments at Revolut with USD to PLN currency conversion.

## Problem description

Revolut provides monthly transaction statements in US dollars. 
If you happen to be a foreign investor you need to pay capital tax in the local national currency of your tax residency e.g. GBP or PLN. 
That means you need to calculate your profit in local currency based on the USD exchange rate of the day of your purchase and then of the day you sell. 
If you buy the same stock a few times with different exchange rates, and you sell it in different amounts on different days, the problem becomes quite complex.
My app calculates the profit and 19% tax using FIFO (First In First Out) method.

## Technologies used

- Bootstrap 4.4.1
[https://getbootstrap.com/docs/4.4/](https://getbootstrap.com/docs/4.4/getting-started/introduction/)
- Django 3.2
[https://docs.djangoproject.com/](https://docs.djangoproject.com/en/3.2/)
- JavaScript 
[https://developer.mozilla.org/](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- Python 3.8.6
[https://docs.python.org/3.8/](https://docs.python.org/3.8/)
- sqlite3
[https://sqlite.org/docs.html](https://www.sqlite.org/docs.html)
- other small libraries or packages
[https://dateutil.readthedocs.io/](https://dateutil.readthedocs.io/en/stable/parser.html)

## Distinctiveness and Complexity

Once a user is logged in, 
the user can upload a text file with transactions copied from their Revolut statement file.

*E.g.*

03/16/2020 03/17/2020 USD BUY EBAY - EBAY INC COM - TRD EBAY B 3 at 20.00 Agency. 3 20.00 (60.00)
03/19/2020 03/18/2020 USD SELL EBAY - EBAY INC COM - TRD EBAY S 2 at 30.00 Agency. -2 30.00 60.00

The application reads the file context, parses all transactions, 
inserts them to the SQLight database and makes calculations.
In order to see the profit and the tax to pay, user needs to click '**My Transactions**'.


## Files created

Inside a directory called Revcalc is an application named *calcapp*.
Inside that application is a folder named *static* where all static files are stored:
- script.js file is JavaScript code to give web pages interactive elements that engage a user, like adaptable menu.
- style.css file is CSS code to describe the presentation of the document.

Another folder inside Revcalc directory named *templates* contains all HTML files.
In the models.py file are all Django model classes.
Views.py takes a web request and returns a web response.
Urls.py file defines the mapping between URLs and views.
Forms.py contain Django forms code.
And the admin.py file is used to display my models in the Django admin panel.


## GUI 

Menu is defined in layout.html.  
Form to register new user is defined in register.html and uses 'register' function in views.py.  
Form to login is defined in login.html and uses 'login_view' function in views.py.   
Form for uploading new txt file with transactions copied from monthly steatment from Revolut is defined in load_data.html and uses 'load_data' function in views.py.  
List of document uploaded so far is defined in load_data.html and uses 'load_data' function in views.py.  
List of transactions uploaded so far is defined in my_transactions.html and uses 'my_transactions' function in views.py.  


## How to run the application

1. Clone the code: `git clone https://github.com/Maciek-cod/Rev-calc.git`
2. Open bash terminal at your local server and get into Revcalc directory.
3. Install virtual environment with `python3 -m venv myvenv` command for Linux and OS X, or `python -m venv myvenv` command for Windows.
4. After installing virtual environment start it by typing `source myvenv/bin/activate` for Linux and OS X, or `myvenv\Scripts\activate` command for Windows.
5. Run `pip install -r requirements.txt` command.
6. Then run command `python manage.py runserver`.
7. Copy the url 'http://127.0.0.1:8000/' and open it in your local browser.
8. The website is now running.


## How to use the application

1. Create new account. 
2. Create txt file with transactions coppied from your revolut trading steatment on your local server.
3. Click Load data and upload the txt file to the database.
4. Click 'Report' to view results of all transactions calculations.
5. Click 'My transactions' to see all uploaded transactions sell details.


### To view an example report, please log in using the following credentials:
[Revcalc](https://revcalc.pythonanywhere.com/)

Username: demo
Password: demo


## Possible improvments

- Conversion from USD to GBP and other currencies according to local tax regulations.
- Downloadable Pdf report
- Sales forecast for user's active shares
- Personalised investings statistics
- Improved interface designs 