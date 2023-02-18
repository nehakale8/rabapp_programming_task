# RABapp Programming Task for Machado lab

Challenge Link : (https://github.com/machado-lab/programming-challenge)

Hi! This is a single-page Web Application developed to view the population and movement of animal species.

Technologies Used : Java Springboot, MySQL, Angular, HTML, CSS, Typescript, Bootstrap.

Author : Neha Rajesh Kale

## About the Application
The Application is a single-page web application and all activities are asynchronously performed, ie. the whole page is not refreshed/reloaded. Following are the main activities:
1. Population
- List of all farms is loaded in a table which shows all details about the farm.
- Details include: Name, Address, City, State, Postal Code, Latitude & Longitude.
- The grid also contains the current total count of animals present at the premise.
2. Movements
- List of all movement records is loaded in a table which shows all movement related details.
- Details include: Company Name, Species, Reason, Moved Count, Start Date, Origin Premise Id & Destination Premise Id.
- A provision to add a movement record is provided within the component, which adds a row in the table (without reloading the webpage or the whole grid).
- Upon adding a new movement record, the population data also gets updated accordingly.


## Pre-Requisites
1. **Java**:
- For the backend, Java is required to be installed on the system.
- Installation link is available [here](#resources-used) in **Backend/Java Springboot** section. <br />
- Ensure that the ```JAVA_HOME``` environment variable is configured. <br />
- To check if Java has been installed correctly on the system, run the following command on cmd. <br />
    ```console
    java -version
    ```
2. **Maven**:
- Maven needs to be installed to run the command which would publish the web application on localhost. <br />
- Installation link is available [here](#resources-used) in **Backend/Java Springboot** section. <br />
- You can download the zip file, unzip it and paste it in the Program Files folder. <br />
- Additionally, add the path of bin folder to the ```PATH``` environment variable. <br />
- To check if Maven has been installed correctly on the system, run the following command on cmd. <br />
    ```console
    mvn -v
    ```    
3. **Node.js**:
- Node.js needs to be installed to run the Angular application on the system. <br />
- Installation link is available [here](#resources-used) in **Frontend/Node.js** section. <br />
- To check if Node.js has been installed correctly on the system, run the following command on cmd. <br />
    ```console
    node -v
    npm -v
    ```
- Along with Node.js, Angular CLI needs to be installed as well. <br />
- To install Angular CLI, run the following command in cmd (After installation of Node and NPM). <br />
    ```console
    npm install -g @angular/cli
    ```
- To check if CLI has been installed correctly on the system, run the following command on cmd. <br />
    ```console
    ng v
    ```
4. **MySQL**
- The database used is MySQL. It can be installed from [here](#resources-used).
- Run the script file provided [here]
- Log into your mysql first using:
```
mysql -u yourusername -p yourpassword
```
- Then create a database:
```
mysql>CREATE DATABASE a_new_database_name
```
- Execute mysql statements that have been written in a text file using the following command:
```
mysql -u yourusername -p yourpassword a_new_database_name < text_file
```
- Before running the application, modify the [application.properties](https://github.com/nehakale8/rabapp_backend/blob/8273aef27ecb09ef1d3828d03296421ce7ab9038/src/main/resources/application.properties) file with the password configured for ```postgres``` username

```
...
spring.datasource.url=jdbc:mysql://localhost:3306/rabapp_task?allowPublicKeyRetrieval=true&useSSL=false
spring.datasource.username=<ENTER USERNAME HERE>
spring.datasource.password=<ENTER PASSWORD HERE>
...
```
## Getting started

1. Clone the github [repository](https://github.com/nehakale8/rabapp_programming_task.git) using the command given
2. Go to the backend folder. Start backend server.
3. Go to the frontend folder. Start frontend server.

## How to run the app?

_**Note:** This project is not meant to be run in a production environment. The commands below will start development servers only._

```
git clone --recursive https://github.com/nehakale8/rabapp_programming_task.git
cd rabapp_programming_task
cd rabapp_backend
mvnw spring-boot:run
```


After the backend is up and running


```
cd ..
cd rabapp_frontend
ng serve
```

## Resources Used
- **Backend**
    - **Java Springboot**
        - [Java Installation](https://www.oracle.com/java/technologies/downloads/#jdk18-windows)
        - [Initialize Springboot application](https://start.spring.io/) 
        - [Maven Download](https://maven.apache.org/download.cgi)
        - [Maven Installation Steps](https://maven.apache.org/install.html)
        - [Eclipse IDE](https://www.eclipse.org/downloads/packages/release/kepler/sr2/eclipse-ide-java-ee-developers)
    - **MySQL**
        - [Download Setup](https://dev.mysql.com/doc/refman/8.0/en/installing.html)
        - [Documentation](https://dev.mysql.com/doc/)
    - **Postman** - [Download Setup](https://www.postman.com/downloads/)
- **Frontend**
    - **Node.js** 
        - [Download Setup](https://nodejs.org/en/download/)
        - [Documentation](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
    - **Angular** - [Documentation](https://angular.io/docs)
    - **Bootstrap** - [Documentation](https://getbootstrap.com/docs/4.0/getting-started/introduction/)

## Application Demo
The [Demo](https://drive.google.com/drive/folders/1PQurcdbnx3GmGBoEUmeYy0T_dpkEP9JP?usp=share_link) folder contains the screen recording of the application to demonstrate the various features of the application.

#### APIs

| Endpoint               | Request Type | Parameters                                                 | Response                               | Remarks                                                                                                                                           |
| ---------------------- | ------------ | ---------------------------------------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/population` | GET          | NA                                                         | `{status: boolean, data: JSON}`        | Returns a list of farms with the lat long information and other data                         |
| `/population/{pid}` | GET          | premise id                                                         | `{status: boolean, data: JSON}`        | Returns a particular farm with the lat long information and other data                         |
| `/movements`  | GET          | NA                                                         | `{status: boolean, data: JSON}`        | Returns a list of Movements data with information about origin, destination, shipment start date, count of items moved etc.            |
| `/movements`  | POST          | form data                                                         | `{status: boolean, data: JSON}`        | Returns a the created movement data.        |
| `/map`           | GET          | NA                                                         | `{status: boolean, data: string}`      | Used to load data from the CSV file into the Database. Developoed for internal use. Not to be used or called from an external location and/or UI. |
