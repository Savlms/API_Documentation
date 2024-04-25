
# GMO Crop API Documentation

# Introduction
The GMO Crop API provides access to detailed information about genetically modified organisms (GMO) crops. This documentation is intended for developers, testers, project managers, and stakeholders interested in obtaining comprehensive descriptions of GMO crops for various purposes.

## Base URL
https://api.gmocrops.com/v1


# Endpoints

## Retrieve All GMO Crops
Retrieve a list of all genetically modified crops available in the database.
- URL: `/gmocrops`
- Method: `GET`
- Parameters: None
- Response:
  - 200 OK: Returns a JSON array of GMO crop objects, each containing the following fields:

    - `id` (integer): Unique identifier for the GMO crop.
    - `name` (string): Common name of the GMO crop.
    - `scientific_name` (string): Scientific name of the GMO crop.
    - `description` (string): Detailed description of the GMO crop, including its genetic modifications, traits, and applications.
    - `benefits` (string): Potential benefits or advantages of the GMO crop.
    - `concerns` (string): Ethical, environmental, or health-related concerns associated with the GMO crop.

  - Example:
    ```json
    [
      {
        "id": 1,
        "name": "Roundup Ready Soybean",
        "scientific_name": "Glycine max (L.) Merr.",
        "description": "Roundup Ready Soybean is genetically engineered to be resistant to the herbicide glyphosate.",
        "benefits": "Allows farmers to effectively control weeds and reduce herbicide usage.",
        "concerns": "Potential development of herbicide-resistant weeds and environmental impacts."
      },

      {
        "id": 2,
        "name": "Bt Corn",
        "scientific_name": "Zea mays",
        "description": "Bt Corn is genetically modified to produce insecticidal proteins derived from the bacterium Bacillus thuringiensis (Bt).",
        "benefits": "Offers protection against certain pests, reducing the need for chemical insecticides.",
        "concerns": "Possible harm to non-target organisms and development of pest resistance."
      },
      
    ]
    

## Retrieve GMO Crop by ID
Retrieve detailed information about a specific GMO crop based on its unique identifier.

- URL: `/gmocrops/{id}`
- Method: `GET`
- Parameters:
  - `{id}` (integer): The unique identifier of the GMO crop.
- Response:
  - 200 OK: Returns a JSON object with the details of the specified GMO crop.
  - 404 Not Found: If the GMO crop with the specified ID does not exist.
  - Example:
    ```json
    {
      "id": 1,
      "name": "Roundup Ready Soybean",
      "scientific_name": "Glycine max (L.) Merr.",
      "description": "Roundup Ready Soybean is genetically engineered to be resistant to the herbicide glyphosate.",
      "benefits": "Allows farmers to effectively control weeds and reduce herbicide usage.",
      "concerns": "Potential development of herbicide-resistant weeds and environmental impacts."
    }
    

## Retrieve GMO Crop by Description/Username
Retrieve detailed information about a specific GMO crop based on its unique identifier.

- URL: `/gmocrops/{Username}`
- Method: `GET`
- Parameters:
  - `{username}` (string): The unique identifier for the description  of the GMO crop.
- Response:
  - 200 OK: Returns a JSON object with the details of the specified GMO crop.
  - 404 Not Found: If the GMO crop with the specified Username does not exist.
  - Example:
    ```json
    {
      "id": 1,
      "Username": "Roundup Ready Soybean",
      "scientific_name": "Glycine max (L.) Merr.",
      "description": "Roundup Ready Soybean is genetically engineered to be resistant to the herbicide glyphosate.",
      "benefits": "Allows farmers to effectively control weeds and reduce herbicide usage.",
      "concerns": "Potential development of herbicide-resistant weeds and environmental impacts."
    }

## Search GMO Crops
Search for GMO crops based on keywords or criteria.

- URL: `/gmocrops/search`
- Method: `GET`
- Parameters:
  - `query` (string, optional): Keyword(s) to search for in GMO crop names or descriptions.
- Response:
  - 200 OK: Returns a JSON array of GMO crop objects matching the search criteria.
  - Example:
    ```json
    [
      {
        "id": 1,
        "name": "Roundup Ready Soybean",
        "scientific_name": "Glycine max (L.) Merr.",
        "description": "Roundup Ready Soybean is genetically engineered to be resistant to the herbicide glyphosate.",
        "benefits": "Allows farmers to effectively control weeds and reduce herbicide usage.",
        "concerns": "Potential development of herbicide-resistant weeds and environmental impacts."
      },
      
    ]


## Update GMO Crop by Username
Updates information about a specific GMO crop based on its unique identifier.

- URL: `/gmocrops/{Username}`
- Method: `PATCH`
- Parameters:
  - `{username}` (string): The unique identifier for the description  of the GMO crop.
  -  `{id}` (integer): The unique identifier of the GMO crop.
- Response:
  - 200 OK: Returns a JSON object with the details of the specified GMO crop.
  - 404 Not Found: If the GMO crop with the specified Username does not exist.
  - Example:
    ```json
    {
      "id": 1,
      "Username": "Roundup Ready Soybean",
      "scientific_name": "Glycine max (L.) Merr.",
      "description": "Roundup Ready Soybean is genetically engineered to be resistant to the herbicide glyphosate.",
      "benefits": "Allows farmers to effectively control weeds and reduce herbicide usage.",
      "concerns": "Potential development of herbicide-resistant weeds and environmental impacts."
    }

## Delete GMO Crop by Username/ID
Deletes information about a specific GMO crop based on its unique identifier.

- URL: `/gmocrops/{Username}`
- Method: `DELETE`
- Parameters:
  - `{username}` (string): The unique identifier for the description  of the GMO crop.
  -  `{id}` (integer): The unique identifier of the GMO crop.
- Response:
  - 200 OK
  - 404 Not Found: If the GMO crop with the specified Username or Id does not exist.
  - Example:
    ```json
    {
      "id": 1,
      "Username": "Roundup Ready Soybean",
      "scientific_name": "Glycine max (L.) Merr.",
      "description": "Roundup Ready Soybean is genetically engineered to be resistant to the herbicide glyphosate.",
      "benefits": "Allows farmers to effectively control weeds and reduce herbicide usage.",
      "concerns": "Potential development of herbicide-resistant weeds and environmental impacts."
    }

# Usage
To access GMO crop data from the API, make HTTP GET requests to the specified endpoints using the provided base URL.

Example using Node.js

```javascript
const axios = require('axios');

// Retrieve all GMO crops
axios.get('https://api.gmocrops.com/v1/gmocrops')
  .then(response => {
    console.log('All GMO crops:', response.data);
  })
  .catch(error => {
    console.error('Error retrieving GMO crops:', error);
  });


// Retrieve GMO crop by ID (e.g., ID = 1)
axios.get('https://api.gmocrops.com/v1/gmocrops/1')
  .then(response => {
    console.log('GMO crop details:', response.data);
  })
  .catch(error => {
    console.error('Error retrieving GMO crop details:', error);
  });
```



# Conclusion
The GMO Crop API offers a valuable resource for obtaining detailed information about genetically modified crops. Developers can utilize this data to integrate GMO crop information into applications, testers can verify functionality, and stakeholders can make informed decisions regarding GMO crop usage.
