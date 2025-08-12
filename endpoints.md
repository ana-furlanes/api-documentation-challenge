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
