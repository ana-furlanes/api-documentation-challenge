# API Endpoints

This section provides technical details for the main API endpoints, including required parameters, cURL examples, and expected responses.

## 1. GET /employee/{id}

This endpoint fetches the details of a specific employee using their unique ID.

* **URL:** `/employee/{id}`
* **Method:** `GET`

### Path Parameters

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `id` | `integer` | **Required.** The unique ID of the employee to be fetched. |

### Example Request (cURL)

```bash
curl -X GET [https://dummy.restapiexample.com/api/v1/employee/1](https://dummy.restapiexample.com/api/v1/employee/1)
```

### Expected Response (200 OK)

A successful response returns a status of `200 OK` and a JSON object containing the employee's details.

```
{
    "status": "success",
    "data": {
        "id": "1",
        "employee_name": "Tiger Nixon",
        "employee_salary": "320800",
        "employee_age": "61",
        "profile_image": ""
    },
    "message": "Successfully! Record has been fetched."
}
```

## 2. POST /create

This endpoint creates a new employee record.

* **URL:** `/create`
* **Method:** `POST`

### Resquest Body

This endpoint requires a JSON object in the request body with the following fields:

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `name` | `string` | **Required.** The employee's full name. |
| `salary` | `string` | **Required.** The employee's salary. |
| `age` | `string` | **Required.** The employee's age. |

### Example Request (cURL)

```bash
curl -X POST -H "Content-Type: application/json" -d '{"name":"seu nome","salary":"123","age":"23"}' [https://dummy.restapiexample.com/api/v1/create](https://dummy.restapiexample.com/api/v1/create)
```

### Expected Response (200 OK)

A successful response returns a status of `200 OK` and a JSON object with the details of the newly created employee.

```
{
    "status": "success",
    "data": {
        "name": "seu nome",
        "salary": "123",
        "age": "23",
        "id": 100
    },
    "message": "Successfully! Record has been added."
}
```
---

## 3. GET /employees

This endpoint fetches the details of all employees.

* **URL:** `/employees`
* **Method:** `GET`

### Example Request (cURL)

```bash
curl -X GET [https://dummy.restapiexample.com/api/v1/employees](https://dummy.restapiexample.com/api/v1/employees)
```

### Expected Response (200 OK)

A successful response returns a status of `200 OK` and a JSON object containing a list of all employee records.

```
{
    "status": "success",
    "data": [
        {
            "id": "1",
            "employee_name": "Tiger Nixon",
            "employee_salary": "320800",
            "employee_age": "61",
            "profile_image": ""
        },
        {
            "id": "2",
            "employee_name": "Garrett Winters",
            "employee_salary": "170750",
            "employee_age": "63",
            "profile_image": ""
        }
    ],
    "message": "Successfully! All records has been fetched."
}
```

## 4. PUT /update/{id}

This endpoint updates an existing employee record using their unique ID.

* **URL:** `/update/{id}`
* **Method:** `PUT`

### Path Parameters

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `id` | `integer` | **Required.** The unique ID of the employee to be updated. |

### Resquest Body (JSON)

This endpoint requires a JSON object in the request body with the fields to be updated.

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `name` | `string` | The new name of the employee. |
| `salary` | `string` | The new salary of the employee. |
| `age` | `string` | The employee's age. |

### Example Request (cURL)

```bash
curl -X PUT -H "Content-Type: application/json" -d '{"name":"João Silva","salary":"99999","age":"30"}' [https://dummy.restapiexample.com/api/v1/update/1](https://dummy.restapiexample.com/api/v1/update/1)
```

### Expected Response (200 OK)

A successful response returns a status of `200 OK` and a JSON object confirming the update.

```
{
    "status": "success",
    "data": {
        "name": "João Silva",
        "salary": "99999",
        "age": "30"
    },
    "message": "Successfully! Record has been updated."
}
```

## 5. DELETE /delete/{id}

This endpoint removes an employee record using their unique ID.

* **URL:** `/delete/{id}`
* **Method:** `DELETE`

### Path Parameters

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `id` | `integer` | **Required.** The unique ID of the employee to be deleted. |

### Example Request (cURL)

```
curl -X DELETE [https://dummy.restapiexample.com/api/v1/delete/1](https://dummy.restapiexample.com/api/v1/delete/1)
```

### Expected Response (200 OK)

A successful response returns a status of `200 OK` and a JSON object confirming the delection.

```
{
    "status": "success",
    "data": "1",
    "message": "Successfully! Record has been deleted"
}
```
