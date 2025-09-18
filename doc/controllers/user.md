# User

Operations about user

Find out more about our store: [http://swagger.io](http://swagger.io)

```ts
const userController = new UserController(client);
```

## Class Name

`UserController`

## Methods

* [Create Users With List Input](../../doc/controllers/user.md#create-users-with-list-input)
* [Get User by Name](../../doc/controllers/user.md#get-user-by-name)
* [Update User](../../doc/controllers/user.md#update-user)
* [Delete User](../../doc/controllers/user.md#delete-user)
* [Logout User](../../doc/controllers/user.md#logout-user)
* [Create User](../../doc/controllers/user.md#create-user)
* [Create Users With Array Input](../../doc/controllers/user.md#create-users-with-array-input)
* [Login User](../../doc/controllers/user.md#login-user)


# Create Users With List Input

Creates list of users with given input array

:information_source: **Note** This endpoint does not require authentication.

```ts
async createUsersWithListInput(
  body: User[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[]`](../../doc/models/user.md) | Body, Required | List of user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: User[] = [
  {
  }
];

try {
  const { result, ...httpResponse } = await userController.createUsersWithListInput(body);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Get User by Name

Get user by user name

:information_source: **Note** This endpoint does not require authentication.

```ts
async getUserByName(
  username: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<User>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | The name that needs to be fetched. Use user1 for testing. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`User`](../../doc/models/user.md).

## Example Usage

```ts
const username = 'username0';

try {
  const { result, ...httpResponse } = await userController.getUserByName(username);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Update User

This can only be done by the logged in user.

:information_source: **Note** This endpoint does not require authentication.

```ts
async updateUser(
  username: string,
  body: UserRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | name that need to be updated |
| `body` | [`UserRequest`](../../doc/models/user-request.md) | Body, Required | Updated user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const username = 'username0';

const body: UserRequest = {
};

try {
  const { result, ...httpResponse } = await userController.updateUser(
    username,
    body
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid user supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Delete User

This can only be done by the logged in user.

:information_source: **Note** This endpoint does not require authentication.

```ts
async deleteUser(
  username: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | The name that needs to be deleted |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const username = 'username0';

try {
  const { result, ...httpResponse } = await userController.deleteUser(username);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Logout User

Logs out current logged in user session

:information_source: **Note** This endpoint does not require authentication.

```ts
async logoutUser(
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await userController.logoutUser();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Create User

This can only be done by the logged in user.

:information_source: **Note** This endpoint does not require authentication.

```ts
async createUser(
  body: UserRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`UserRequest`](../../doc/models/user-request.md) | Body, Required | Created user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: UserRequest = {
};

try {
  const { result, ...httpResponse } = await userController.createUser(body);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Create Users With Array Input

Creates list of users with given input array

:information_source: **Note** This endpoint does not require authentication.

```ts
async createUsersWithArrayInput(
  body: User[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[]`](../../doc/models/user.md) | Body, Required | List of user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: User[] = [
  {
  }
];

try {
  const { result, ...httpResponse } = await userController.createUsersWithArrayInput(body);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Login User

Logs user into the system

:information_source: **Note** This endpoint does not require authentication.

```ts
async loginUser(
  username: string,
  password: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Query, Required | The user name for login |
| `password` | `string` | Query, Required | The password for login in clear text |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const username = 'username0';

const password = 'password4';

try {
  const { result, ...httpResponse } = await userController.loginUser(
    username,
    password
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username/password supplied | `ApiError` |

