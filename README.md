# Stock Management System


## Overview

The Stock Management System (SMS) is a comprehensive web application designed for managing and tracking inventory, sales, and user permissions. Developed using Django, this project showcases the integration of various features necessary for effective stock management in a commercial environment. The application supports functionalities such as product registration, batch management, sales tracking, user management, and permission control. It is designed to handle both perishable and non-perishable items, providing a robust solution for inventory control.

- ### Distinctiveness and Complexity
    - The dynamic stock management system distinguishes itself from other projects in the course through its unique focus and complexity. Unlike the other course projects, which cover search engines, wikis, auctions, email clients, and social networks, my application addresses real-world stock management challenges, offering a sophisticated solution that combines both front-end and back-end technologies.

**Distinctiveness**:

- Business Logic: Manages perishable and non-perishable items with frontend and backend validation to prevent overselling and maintain data integrity.
- Django and JavaScript Integration: Combines Django's backend capabilities with dynamic JavaScript features for interactive sales reports and real-time updates.
- Mobile Responsiveness: Designed for seamless use on various devices.
- Advanced Features: Includes dynamic sales graphs, interactive filters, and detailed historical tracking.

**Complexity**:
- Data Handling: Uses Django’s ORM for detailed sales, inventory, and batch management with custom validations.
- Dynamic UI: Implements advanced JavaScript and AJAX for interactive elements like expandable sales details and real-time graphs.
- Reporting and Filtering: Creates detailed sales reports with various filters and dynamic graphing using Plotly and Matplotlib.
- Security and Permissions: Manages user permissions with Django’s authentication and authorization features.
- Validation: Employs both frontend JavaScript and backend checks to ensure data accuracy and prevent invalid transactions.


# Files and Structure


The `PROJECTFINAL/` project root directory contains the following structure:
- **`members/`**: Root directory of the `members` app.
  - **`templates/authenticate/`**: Directory containing HTML templates related to authentication and user management.
    - **`login.html`**: Login page where users can access their accounts.
    - **`manage_permissions.html`**: Permission management page allowing administrators to adjust permissions for different roles.
    - **`register_user.html`**: User registration page allowing the creation of new accounts.
  - **`forms.py`**: Contains `RegisterUserForm`, which defines the form used for new user registration. This form handles data collection and validation during user registration.
  - **`views.py`**: Contains the view functions for the `members` app.
    - **`login`**: Function handling user login, managing authentication, and redirecting to the appropriate page after login.
    - **`manage_permissions`**: Function allowing administrators to manage user permissions. This function displays the `manage_permissions.html` page and processes permission updates as needed.

- **`prints/`**: Contains screenshots used in the system tutorial, demonstrating and explaining the functionality of each page.

- **`stock/`**: Main directory for the `stock` app, containing all files related to inventory management.
  - **`templates/screen/`**: Directory containing all HTML pages used in the system.
    - **`add_batch.html`**: Page for adding new product batches to the system.
    - **`add_product.html`**: Page for adding new products to the system.
    - **`index.html`**: Main page of the system, providing an link to the tutorial.
    - **`layout.html`**: Base layout defining the common structure of the HTML pages in the system.
    - **`profit_loss_graph.html`**: Page displaying profit and loss graphs.
    - **`register_discard.html`**: Page for recording discarded items due to expiration.
    - **`register_sale.html`**: Page for recording product sales.
    - **`sales_history.html`**: Page for viewing sales history.
    - **`stock_view.html`**: Page for viewing and managing product stock.
  - **`models.py`**: Defines the database models used in the system:
    - **`Product`**: Model representing products.
    - **`BatchProduct`**: Model representing product batches.
    - **`SalesRecord`**: Model representing sales records.
    - **`mark_expired_batches_on_login.py`**: Script that checks for expired batches when a user logs in and marks them as expired if necessary.
  - **`urls.py`**: Defines the URLs and paths of the system, mapping URLs to corresponding view functions.
  - **`views.py`**: Contains the backend logic of the system, including view functions for manipulating data and rendering HTML pages.

- **`stock_manager/`**: Directory for the `stock_manager` app, containing all files related to settings, urls, .env .
    - **`.env`**: local to put your secret_key to project run.
    - **`settings.py`**: Defines the settings of the project.
    - **`urls.py`**: Defines the urls of the project
  
- **`README.md`**: Contains instructions for running the system and an overview of the project.
- **`requirements.txt`**: Lists all the dependencies required for the project.
- **`tutorial_pages.md`**: Provides a detailed tutorial on each page of the system and explains how the system works.





## Setup and Installation

### Prerequisites

Before following the installation steps, make sure you have the following prerequisites installed on your computer:

1. **Python**: Verify if Python is installed by running `python --version` or `python3 --version` in the terminal. If not installed, download and install it from the official site: [python.org](https://www.python.org/).

2. **Git**: Verify if Git is installed by running `git --version` in the terminal. If not installed, download and install it from the official site: [git-scm.com](https://git-scm.com/).

3. **Visual Studio Code** (or another text/code editor) (Optional): To edit and manage the code, it is recommended to install Visual Studio Code: [code.visualstudio.com](https://code.visualstudio.com/).

### Clone the Repository
```bash
MUDAR (EXEMPLO)
git clone "No momento está privado o Repositorio"
cd ProjectFinal
```

### Create and Activate a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Install matplotlib
```bash
pip install matplotlib
```

### Create migrations
```bash
python manage.py makemigrations
```


### Apply Migrations
```bash
python manage.py migrate
```

### Generate a secret_key to put on .env
On the terminal, execute 
```bash
python
```
Execute
```bash
from django.core.management.utils import get_random_secret_key
```
print the secret key on the screen and copy after
```bash
print(get_random_secret_key())
```
To exit digit exit() on the terminal and press enter 

### Put the generate key on the file .env located inside the folder stock_manager
- **`PROJECTFINAL/`**: project root directory contains the following structure:
  - **`members/`**: Root directory of the `members` app.
  - **`prints/`**: Contains screenshots used in the system tutorial, demonstrating and explaining the functionality of each page.
  - **`stock/`**: Main directory for the `stock` app, containing all files related to inventory management.
  - **`stock_manager/`**: Directory for the `stock_manager` app, containing all files related to settings, urls, .env .
      - **`.env`**: local to put your secret_key to project run.  <- PUT INSIDE HERE
      - **`settings.py`**: Defines the settings of the project.
      - **`urls.py`**: Defines the urls of the project 


- **Make sure to keep the .env file secure and avoid sharing it in public repositories. After placing the secret key in the .env file, restart your Django server to apply the changes.**

### Create a Superuser (For Admin Access)
Superuser is the user responsible to grant permissions to regular users in the system
```bash
python manage.py createsuperuser
```

### Run the Development Server
```bash
python manage.py runserver
```

### Remember after closing the application and want to open again put this command on the terminal of the project to re-open the venv
```bash
.\venv\Scripts\activate
```

### Now you run the:
```bash
python manage.py runserver
```

### Access the Application
Open a web browser and navigate to http://127.0.0.1:8000/ to start using the application.


### User Roles and Permissions
- **Superuser**: Has full access to all features, including managing users and permissions.
- **Regular Users**: Can perform operations based on the assigned permissions, such as viewing products and recording sales.
 
## Features

### Product Management

- **Register Products**: Add new products with name, description, and perishable status.
- **Product Details**: Manage detailed product information, including batch and sales history.

###  Batch Management
- **Batch Registration**: Register batches with details like batch ID, arrival, and expiry dates.
- **Batch Details**: Manage batch specifics, including product associations and quantities.
- **Perishable Items Handling**: 
    - Flag and highlight expired perishable items in red.
    - Exclude expired batches from sales; manage expired items through the discard functionality, recording them as sold at zero value.

###  Sales Tracking
- **Record Sales**: Capture sales data, including items, quantities, prices, and customers.
- **Sales History**: View and filter sales history by date, product, and customer with detailed sale information.

### User Management
- **User Registration**: Add new users with role-based permissions.
- **User Login/Logout**: Secure login and logout.
- **Manage Permissions**: Superusers manage permissions for accessing application functionalities.

### Reporting and Analytics
- **Sales Reports**: Generate sales performance reports, including profit and loss.
- **Dynamic Graphs**: Interactive graphs with filtering options for date ranges and products.
    - **Plotly Integration**:
        - Create customizable graphs with interactive elements.
        - Toggle data series visibility and save graphs as PNG files.
        - Green columns show profit; red columns indicate loss.

### Pagination for Dynamic Pages
- **Paginator**: Divides large datasets into manageable pages to improve load times and navigation.

## Technical Details

### Technologies Used
- **Backend**: Django 5.0.6 for web application framework.
- **Frontend**: HTML, CSS, Bootstrap 4 for styling and layout. Bootstrap 4 was used to ensure that the site is mobile-responsive, providing a seamless user experience across various devices and screen sizes.
- **Database**: SQLite for development; can be configured to use PostgreSQL or other databases for production.
- **JavaScript**: jQuery for interactive elements in the UI, such as expanding sales details.


# Tutorial explaing the pages on the system
- [Tutorial](https://github.com/RanieryN/ProjectFinal/blob/main/tutorial_pages.md)


### Acknowledgements
- **Django Documentation**: For comprehensive guidance on Django features and best practices. Visit the [official Django documentation](https://docs.djangoproject.com/en/stable/) for more information.
- **Bootstrap 4**: For providing responsive design components and styles. Check out the [Bootstrap 4 documentation](https://getbootstrap.com/docs/4.0/getting-started/introduction/) for details on how to use its features.
- **jQuery**: For simplifying JavaScript functionalities and enhancing interactivity. Explore the [jQuery documentation](https://api.jquery.com/) to learn more about its capabilities and how to use them effectively.

- **Python Documentation**: For various Python modules used in the project. Visit the [official Python documentation](https://docs.python.org/3/) for more details on:
  - [collections.defaultdict](https://docs.python.org/3/library/collections.html#collections.defaultdict)
  - [datetime](https://docs.python.org/3/library/datetime.html)
  - [json](https://docs.python.org/3/library/json.html)
  - [typing](https://docs.python.org/3/library/typing.html)
  - [calendar](https://docs.python.org/3/library/calendar.html)
  - [DjangoJSONEncoder](https://docs.djangoproject.com/en/5.0/topics/serialization/)
  - [parse_date](https://docs.djangoproject.com/en/stable/ref/utils/#dateutil)
  - [timezone](https://docs.djangoproject.com/en/5.0/topics/i18n/timezones/)
