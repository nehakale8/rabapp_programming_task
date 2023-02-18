# RABapp Programming Task for Machado lab

Challenge Link : (https://github.com/machado-lab/programming-challenge)

Hi! This is a single-page Web Application developed to view the population and movement of animal species.

Technologies Used : Java Springboot, MySQL, Angular, HTML, CSS, Typescript, Bootstrap.

Author : Neha Rajesh Kale

## Getting started

1. Clone the github [repository](https://github.com/nehakale8/rabapp_programming_task.git) using the command given
2. Go to the backend folder. Start backend server.
3. Go to the frontend folder. Start frontend server.

## How to run the app?

_**Note:** This project is not meant to be run in a production environment. The commands below will start development servers only._

```
git clone --recursive https://github.com/nehakale8/rabapp_programming_task.git
cd rabapp_programming_task

```



#### APIs

| Endpoint               | Request Type | Parameters                                                 | Response                               | Remarks                                                                                                                                           |
| ---------------------- | ------------ | ---------------------------------------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/register`            | POST         | `{email : string, password: string, display_name: string}` | `{status: boolean, data: string/JSON}` | Used for new user registration                                                                                                                    |
| `/login`               | POST         | `{email : string, password: string}`                       | `{status: boolean, data: string/JSON}` | Used to authenticate users. Response may contain error message in case of failing authentications, or logged in user's details in the JSON format |
| `/get_population_data` | GET          | NA                                                         | `{status: boolean, data: JSON}`        | Returns a list of Premises along with their corresponding animal count.                                                                           |
| `/get_movements_data`  | GET          | NA                                                         | `{status: boolean, data: JSON}`        | Returns a list of Movements data with information about origin, destination, shipment start date, count of items moved, lat, long etc.            |
| `/get_premises_data`   | GET          | NA                                                         | `{status: boolean, data: JSON}`        | Returns a list of Premises with the lat long information, mainly used for generating markers on the google map.                                   |
| `/load_data`           | GET          | NA                                                         | `{status: boolean, data: string}`      | Used to load data from the CSV file into the Database. Developoed for internal use. Not to be used or called from an external location and/or UI. |
