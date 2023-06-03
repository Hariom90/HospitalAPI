# HospitalAPI

This is a RESTful API designed specifically for a Hospital, serving the purpose of managing the health records of patients affected by COVID-19. The API offers a range of functionalities that enable the hospital staff, specifically doctors, to register and log in, register patients, and generate reports for each patient visit. Additionally, the API provides endpoints to retrieve a patient's records and filter all reports based on their status.

Built on the Node.js platform and utilizing MongoDB as the database, this API ensures efficient and secure data management. Authentication is implemented using JSON Web Tokens (JWT), ensuring secure access for authorized users. The project follows a well-organized folder structure, separating models, controllers, and routes, which enhances scalability and maintainability.



<hr />

## Installation Options

```
git clone https://github.com/Hariom90/HospitalAPI.git
```
or

Simply download the Zip File and run on your system


### Running on your local system:

 * run the command `npm install` in terminal to install all dependencies
 * run the command `node index` in terminal to start the server on port 8000
 * open up browser and type `localhost:8000` in URL and you're good to go
 
<hr />

## Documentation

Root Hosted Link - () 

## API Routes

### Doctor

-   **POST** `/doctors/register` - Register a new doctor.
-   **POST** `/doctors/login` - Login with a username and password to receive a JWT.
    > Note: All routes except for `/doctors/register` and `/doctors/login` require a valid JWT to be included in the Authorization header of the request. The JWT should have the format `Bearer <token>`.

### Patients

-   **POST** `/patients/register` - Allows a doctor to register a new patient. If the patient already exists, the existing patient info is returned.
-   **POST** `/patients/:id/create_report` - Allows a doctor to create a patients report (JWT Auth enabled)
-   **GET** `/patients/:id/all_reports` - Sends all the reports of a patient oldest to latest. (JWT Auth enabled).

### Reports

-   **GET** `/reports/:status` - List of all the reports of all patients with a specific status. (JWT Auth enabled).

<hr />

### Data that needs to be sent with a route :
    
    a. /doctors/register - name, email, password (Form type data)
    b. /doctors/login - email, password (Form type data).
    c. /patients/register - JWT Token (In Headers), name, phone, age, sex, comorbidity status (Form type data).
    d. /patients/:id/create_report - JWT Token (In Headers), Patient's ID (params), status (Form type data).
    e. /patients/:id/all_reports - JWT Token (In Headers), Patient's ID (params).
    f. /reports/:status - JWT Token (In Headers), status (params).

### Folder Structure

    a. index.js - Server runs here
    b. models - Contains all the models for Doctor, Patient, Report.
    c. routes - Contains all the routes.
    d. controllers - Contains all the controllers.
    e. config - Contains all the config files.
## Authors

- (https://github.com/Hariom90/HospitalAPI)

  

