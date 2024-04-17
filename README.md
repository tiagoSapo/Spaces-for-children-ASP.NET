# SpacesForChildren

This project is a web application developed in ASP.NET MVC 5 and C#, presenting various functionalities and concepts of this framework. The application is named "SpacesForChildren" and presents a structure that allows the management of information about institutions, services, and evaluations, simulating a scenario of searching for places for children.

## Main Features

- **User Registration and Authentication:** The system offers different access profiles, including General, Parents, Institution, and Administrator, each with specific and customized functionalities.
  
- **General Profile:** Allows viewing a list of institutions, obtained evaluations, contacts, and other relevant information.
  
- **Parents Profile:** Includes functionalities such as registration, information requests, viewing the history of evaluations, specifying preferences for searches, and evaluating institutions.
  
- **Institution Profile:** Allows registration of institutions, access to presented information, list of services offered, forms for activities, viewing evaluations made by parents, among other functionalities.
  
- **Administrator Profile:** Allows general management of the system and data in the database, including approval of institution records.

- **Database Management:** Uses SQL Server 2016/2017 (localdb) and Entity Framework 6.0 for data manipulation and analysis.

## Additional Information

### Functionality Details

#### Parent Profile
The General profile represents all users who have a registered Parent account on the website. With the Parent profile, users can only access the Parent tab and its respective links (View available institutions, create a new account, enroll children in institutions, make requests to institutions, view institution fees, etc.).

#### Institution Profile
The Institution profile represents all users who have a registered Institution account on the website. With the Institution profile, users can only access the Institutions tab and its respective links (Sign in with an existing account, create a new account, view enrolled students, view institution evaluations, add more services, respond to parent requests, etc.).

#### Administrator Profile
The Administrator profile represents all users who have a registered Administrator account on the website. With the Administrator profile, users can access all tabs of the website and their respective functionalities. The Administrator can view and modify all tables in the database, authorize institutions in the system, and perform all functionalities of other profiles.

#### General Profile
The General profile represents all users who do not have a registered account on the website. With the General profile, users can only access the General tab and its respective links (View registered institutions and parents on the website).

### Other Information

#### Database
"Data Model" of the database:

- Parent - Child Relationship (1:N)
- Institution - Child Relationship (1:N)
- Institution - Education Relationship (M:N)
- Education - Child Relationship (1:N)
- Education - Discipline Relationship (1:N)

The database also contains three additional entities: ParentAuthorization, InstitutionAuthorization, and Requests. When a new Parent account is created, it is initially stored in the ParentAuthorization entity until the institution approves it. Once approved, it is moved to the Parent entity. The same process applies to the Institution entity. The Requests entity stores all requests made by parents to institutions. The database was developed using the Entity Framework 6 ORM, using the "code first" approach and "fluent API" for entity relationships and naming conventions.

#### Access Management
A user who does not register on the website only has access to the general tab. To access other tabs, the user must register and associate their account with the desired profile in the registration form. If a user attempts to access other tabs without logging in, a login form will appear, as these tabs are restricted to users with administrator, institution, and parent profiles.

Once registered, the user is associated with the desired profile. Institutions and parents must register separately and await approval from the administrator. After approval, they can log in and access additional functionalities.

#### Technologies / Features Used
- Data annotations for view model parameter/property validation.
- Remote data annotation for JavaScript-based validation of institution, parent, and child names.
- AJAX for dynamic loading of institution lists based on selected district.
- jQuery script for updating the "Education Option" dropdown list based on the selected institution.
- Identity for access restriction based on user profiles.
- Developed using ASP.NET MVC 5 framework.
- Developed in Microsoft Visual Studio 2015 Update 3 with .NET framework 4.6.1.
- Bootstrap template used: Cosmo from https://bootswatch.com/3/cosmo/. Minor customizations were made to this template (in bootstrap_final.css and Site.css files) for colors, margins, image curvature, etc.

## Final Notes

The project aims to demonstrate the functioning of an ASP.NET MVC application, presenting a simulated solution for managing information about institutions, services, and evaluations related to children.
