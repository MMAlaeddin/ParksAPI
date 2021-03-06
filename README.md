# National Parks API Application



#### By: **Mariam Alaeddin**, April 3, 2020

## Description

_An API that lets you query National Parks. Find out how many climbs you can squeeze into your trip, find out how many campgrounds there are and places to grab last minute "left-behinds".  You can also search our database by city, state and name!_

## Endpoint Specs
| Endpoint | Http Action | Return Data |
| -------- | :---------: | :---------: |
| /api/parks | GET | List ( "parkId": 1, "name": "Crater Lake National Park", etc. ) |
| /api/parks | POST | New Park ( "parkId": 5, "name": "Death Valley National Park", etc) |
| /api/parks/1 | GET | ( "parkId": 1, "name": "Crater Lake National Park", etc. ) |
| /api/parks/1 | PUT | ( "parkId": 1, "name": "Crater Lake National Park", "description": "It's HOT!" ) |
| /api/parks/1 | DELETE | (  ) |

## Specs user stories:
| Specification | Example Input | Example Output |
| ------------- |:-------------:| -------------------:|
| If user visits '/' root route, the application displays a splash page with links to '/Parks', '/Parks'  and '/Users' | user visits '/' route | application displays homepage |
| Application allows a user to register for an account with Identity | user clicks "login/register" option on splash page, then completes form at '/Account/Register' | application creates new user account and redirects to '/Login' |
| Application allows a registered user to login | registered user clicks "log in" option at '/Account' | application redirects to '/Account/Login' |
| Application allows a registered user to logout | registered user clicks "logout" option at '/Account' | application logs out of user account |
| Only registered, logged-in users are able to create, update, and delete Parks | user is not logged in and/or not registered and clicks "add review", "edit review", or "delete review" | user redirected to login page |
If user visits '/Parks' route, the application displays all Parks in the database, ordered from highest rated to lowest rated | user visits '/Parks' | application displays list of all Parks in order of rating |
| If a registered user clicks "add new destination" link at '/Parks', the application redirects to a form ('/Parks/Create') for adding a new destination | registered user clicks "add new destination" | the application redirects to form at 'Parks/Create' |
| When a registered user submits the new destination form, the application adds the new destination to the Parks table of the travel database and redirects to '/Parks' | registered user submits new destination form | the application adds new destination to Parks table and redirects to '/Parks' |
| A registered user can delete a destination from the list of all Parks | registered user selects "delete destination" option | application deletes destination from database |
| A registered user can edit a destination from the list of all Parks | registered user selects "edit destination" | application redirects to edit form |
| If user visits '/Parks' route, the application displays all Parks in the database, ordered from highest rated to lowest rated | user visits '/Parks' | application displays list of all Parks in order of rating |
| If a registered user clicks "add new review" link at '/Parks', the application redirects to a form ('/Parks/Create') for adding a new review | registered user clicks "add new review" | the application redirects to form at 'Parks/Create' |
| When a registered user submits the new review form, the application adds the new review to the Parks table of the travel database and redirects to '/Parks' | registered user submits new review form | the application adds new review to Parks table and redirects to '/Parks' |
| A registered user can delete a review from the list of all Parks | registered user selects "delete review" option | application deletes review from database |
| A registered user can edit a review from the list of all Parks | registered user selects "edit review" | application redirects to edit form |

## Setup/Installation Requirements

### Install .NET Core

#### on macOS:
* _[Click here](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-2.2.106-macos-x64-installer) to download a .NET Core SDK from Microsoft Corp._
* _Open the file (this will launch an installer which will walk you through installation steps. Use the default settings the installer suggests.)_

#### on Windows:
* _[Click here](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-2.2.203-windows-x64-installer) to download the 64-bit .NET Core SDK from Microsoft Corp._
* _Open the .exe file and follow the steps provided by the installer for your OS._

#### Install dotnet script
_Enter the command ``dotnet tool install -g dotnet-script`` in Terminal (macOS) or PowerShell (Windows)._

### Install MySQL

#### on macOS:
_Download the MySQL Community Server DMG File [here](https://dev.mysql.com/downloads/file/?id=484914). Follow along with the installer until you reach the configuration page. Once you've reached Configuration, set the following options (or user default if not specified):_
* use legacy password encryption
* set password (and change the password field in appsettings.json file of this repository to match your password)
* click finish
* open Terminal and enter the command ``echo 'export PATH="/usr/local/mysql/bin:$PATH"' >> ~/.bash_profile`` if using Git Bash.
* Verify MySQL installation by opening Terminal and entering the command ``mysql -uroot -p{your password here, omitted brackets}``. If you gain access to the MySQL command line, installation is complete. An error (e.g., -bash: mysql: command not found) indicates something went wrong.

#### on Windows:
_Download the MySQL Web Installer [here](https://dev.mysql.com/downloads/file/?id=484919) and follow along with the installer. Click "Yes" if prompted to update, and accept license terms._
* Choose Custom setup type
* When prompted to Select Products and Features, choose the following: MySQL Server (Will be under MySQL Servers) and MySQL Workbench (Will be under Applications)
* Select Next, then Execute. Wait for download and installation (can take a few minutes)
* Advance through Configuration as follows:
  - High Availability set to Standalone.
  - Defaults are OK under Type and Networking.
  - Authentication Method set to Use Legacy Authentication Method.
  - Set password to epicodus. You can use your own if you want but epicodus will be assumed in the lessons.
  - Unselect Configure MySQL Server as a Windows Service.
* Complete installation process

_Add the MySQL environment variable to the System PATH. Instructions for Windows 10:_
* Open the Control Panel and visit _System > Advanced System Settings > Environment Variables..._
* Select _PATH..._, click _Edit..._, then _Add_.
* Add the exact location of your MySQL installation and click _OK_. (This location is likely C:\Program Files\MySQL\MySQL Server 8.0\bin, but may differ depending on your specific installation.)
* Verify installation by opening Windows PowerShell and entering the command ``mysql -uroot -p{your password here, omitted brackets}``. It's working correctly if you gain access to the MySQL command line. Exit MySQL by entering the command ``exit``.

### Clone this repository

_Enter the following commands in Terminal (macOS) or PowerShell (Windows):_
* ``cd desktop``
* ``git clone`` followed by the URL to this repository
* ``cd NationalParksApi.Solution/NationalParks`

_Confirm that you have navigated to the NationalParks directory (e.g., by entering the command_ ``pwd`` _in Terminal)._

## JWT Authentication in Postman

* Download [Postman](https://www.postman.com/downloads/)
* Create POST request with the following info and syntax:
  ``{
    "username": "mariam@mariam.com"
    "password": "Password123"
  }``
* Hit Send
* Copy your "access token" from the body
* Click Authorization tab
* Select "Bearer Token" authorization type.
* Paste your token
* Click the orange Preview Request button to see a    temporary header has been added under the Headers tab. This temporary header is not saved with your request or collection



## Clone the NationalParksApi repository and run the NationalParksAPI

_Enter the following commands in Terminal (macOS) or PowerShell (Windows):_
* ``cd ~``
* ``cd desktop``
* ``git clone https://github.com/MMAlaeddin/NationalParksApi.Solution``
* ``cd NationalParksApi.Solution/NationalParks``
* ``dotnet restore``
* ``dotnet build``
* ``dotnet ef database update``
* ``dotnet run`` or ``dotnet watch run``

## Run this MVC application in another Terminal or PowerShell window

_Run this MVC application by entering the following command in Terminal (macOS) or PowerShell (Windows) at the root of the NationalParksApi directory:_
* ``dotnet run`` or ``dotnet watch run``


## Technologies Used

* Git
* C#
* Visual Studio Code 1.43.1
* dotnet script 0.50.1
* MySQL 8.0.15
* ASP.NET Core MVC 2.2
* Entity Framework Core 2.2
* RestSharp version 106.6.10
* Newtonsoft.Json version 12.0.2
* [Travel API version 1.0](https://github.com/MMAlaeddin/NationalParksApi.Solution)

## License

Licensed under the MIT license.

&copy; 2020 - Mariam Alaeddin