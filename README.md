# Covid-19 India Portal API

Welcome to the COVID-19 India Portal API repository! This API provides access to the COVID-19 data for India, including statistics, cases, testing information, and more.

The COVID-19 India Portal API allows developers to retrieve COVID-19 related data for India. The API provides various endpoints to access data such as daily case counts, state-wise statistics, testing information, vaccination data, and more.

The API provides the following endpoints:

### API 1

#### Path: `/login/`

#### Method: `POST`

**Request**

```
{
  "username": "christopher_phillips",
  "password": "christy@123"
}
```

- **Scenario 1**

  - **Description**:

    If an unregistered user tries to login

  - **Response**
    - **Status code**
      ```
      400
      ```
    - **Body**
      ```
      Invalid user
      ```

- **Scenario 2**

  - **Description**:

    If the user provides an incorrect password

  - **Response**
    - **Status code**
      ```
      400
      ```
    - **Body**
      ```
      Invalid password
      ```

- **Scenario 3**

  - **Description**:

    Successful login of the user

  - **Response**

    Return the JWT Token

    ```
    {
      "jwtToken": "ak2284ns8Di32......"
    }
    ```

### Authentication with Token

- **Scenario 1**

  - **Description**:

    If the token is not provided by the user or an invalid token

  - **Response**
    - **Status code**
      ```
      401
      ```
    - **Body**
      ```
      Invalid JWT Token
      ```

- **Scenario 2**
  After successful verification of token proceed to next middleware or handler

### API 2

#### Path: `/states/`

#### Method: `GET`

#### Description:

Returns a list of all states in the state table

#### Response

```
[
  {
    "stateId": 1,
    "stateName": "Andaman and Nicobar Islands",
    "population": 380581
  },

  ...
]
```

### API 3

#### Path: `/states/:stateId/`

#### Method: `GET`

#### Description:

Returns a state based on the state ID

#### Response

```
{
  "stateId": 8,
  "stateName": "Delhi",
  "population": 16787941
}
```

### API 4

#### Path: `/districts/`

#### Method: `POST`

#### Description:

Creates a district in the district table, `district_id` is auto-incremented

#### Request

```
{
  "districtName": "Bagalkot",
  "stateId": 3,
  "cases": 2323,
  "cured": 2000,
  "active": 315,
  "deaths": 8
}
```

#### Response

```
District Successfully Added
```

### API 5

#### Path: `/districts/:districtId/`

#### Method: `GET`

#### Description:

Returns a district based on the district ID

#### Response

```
{
  "districtId": 322,
  "districtName": "Palakkad",
  "stateId": 17,
  "cases": 61558,
  "cured": 59276,
  "active": 2095,
  "deaths": 177
}
```

### API 6

#### Path: `/districts/:districtId/`

#### Method: `DELETE`

#### Description:

Deletes a district from the district table based on the district ID

#### Response

```
District Removed

```

### API 7

#### Path: `/districts/:districtId/`

#### Method: `PUT`

#### Description:

Updates the details of a specific district based on the district ID

#### Request

```
{
  "districtName": "Nadia",
  "stateId": 3,
  "cases": 9628,
  "cured": 6524,
  "active": 3000,
  "deaths": 104
}
```

#### Response

```

District Details Updated

```

### API 8

#### Path: `/states/:stateId/stats/`

#### Method: `GET`

#### Description:

Returns the statistics of total cases, cured, active, deaths of a specific state based on state ID

#### Response

```
{
  "totalCases": 724355,
  "totalCured": 615324,
  "totalActive": 99254,
  "totalDeaths": 9777
}

```

<br/>

Use `npm install` to install the packages.

**Export the express instance using the default export syntax.**

**Use Common JS module syntax.**
