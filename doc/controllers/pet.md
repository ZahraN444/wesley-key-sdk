# Pet

Everything about your Pets

Find out more: [http://swagger.io](http://swagger.io)

```ts
const petController = new PetController(client);
```

## Class Name

`PetController`

## Methods

* [Get Pet by Id](../../doc/controllers/pet.md#get-pet-by-id)
* [Update Pet With Form](../../doc/controllers/pet.md#update-pet-with-form)
* [Delete Pet](../../doc/controllers/pet.md#delete-pet)
* [Add Pet](../../doc/controllers/pet.md#add-pet)
* [Update Pet](../../doc/controllers/pet.md#update-pet)
* [Find Pets by Status](../../doc/controllers/pet.md#find-pets-by-status)
* [Upload File](../../doc/controllers/pet.md#upload-file)
* [Find Pets by Tags](../../doc/controllers/pet.md#find-pets-by-tags)


# Get Pet by Id

Returns a single pet

```ts
async getPetById(
  petId: bigint,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet to return |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet`](../../doc/models/pet.md).

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.getPetById(petId);
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
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Pet not found | `ApiError` |


# Update Pet With Form

Updates a pet in the store with form data

```ts
async updatePetWithForm(
  petId: bigint,
  contentType: ContentTypeEnum,
  name?: string,
  status?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet that needs to be updated |
| `contentType` | [`ContentTypeEnum`](../../doc/models/content-type-enum.md) | Header, Required | - |
| `name` | `string \| undefined` | Form, Optional | Updated name of the pet |
| `status` | `string \| undefined` | Form, Optional | Updated status of the pet |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const petId = BigInt(152);

const contentType = ContentTypeEnum.EnumApplicationxwwwformurlencoded;

try {
  const { result, ...httpResponse } = await petController.updatePetWithForm(
    petId,
    contentType
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
| 405 | Invalid input | `ApiError` |


# Delete Pet

Deletes a pet

```ts
async deletePet(
  petId: bigint,
  apiKey?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | Pet id to delete |
| `apiKey` | `string \| undefined` | Header, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.deletePet(petId);
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
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Pet not found | `ApiError` |


# Add Pet

Add a new pet to the store

```ts
async addPet(
  body: PetRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PetRequest`](../../doc/models/pet-request.md) | Body, Required | Pet object that needs to be added to the store |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: PetRequest = {
  name: 'name6',
  photoUrls: [
    'photoUrls1'
  ],
};

try {
  const { result, ...httpResponse } = await petController.addPet(body);
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
| 405 | Invalid input | `ApiError` |


# Update Pet

Update an existing pet

```ts
async updatePet(
  body: PetRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PetRequest`](../../doc/models/pet-request.md) | Body, Required | Pet object that needs to be added to the store |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const body: PetRequest = {
  name: 'name6',
  photoUrls: [
    'photoUrls1'
  ],
};

try {
  const { result, ...httpResponse } = await petController.updatePet(body);
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
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Pet not found | `ApiError` |
| 405 | Validation exception | `ApiError` |


# Find Pets by Status

Multiple status values can be provided with comma separated strings

```ts
async findPetsByStatus(
  status: Status2Enum[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | [`Status2Enum[]`](../../doc/models/status-2-enum.md) | Query, Required | Status values that need to be considered for filter |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet[]`](../../doc/models/pet.md).

## Example Usage

```ts
const status: Status2Enum[] = [
  Status2Enum.Pending,
  Status2Enum.Sold,
  Status2Enum.Available
];

try {
  const { result, ...httpResponse } = await petController.findPetsByStatus(status);
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
| 400 | Invalid status value | `ApiError` |


# Upload File

uploads an image

```ts
async uploadFile(
  petId: bigint,
  additionalMetadata?: string,
  file?: FileWrapper,
  requestOptions?: RequestOptions
): Promise<ApiResponse<MApiResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet to update |
| `additionalMetadata` | `string \| undefined` | Form, Optional | Additional data to pass to server |
| `file` | `FileWrapper \| undefined` | Form, Optional | file to upload |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`MApiResponse`](../../doc/models/m-api-response.md).

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.uploadFile(petId);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Find Pets by Tags

**This endpoint is deprecated.**

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

```ts
async findPetsByTags(
  tags: string[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tags` | `string[]` | Query, Required | Tags to filter by |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### petstore_auth

`read:pets`, `write:pets`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Pet[]`](../../doc/models/pet.md).

## Example Usage

```ts
const tags: string[] = [
  'tags5',
  'tags6'
];

try {
  const { result, ...httpResponse } = await petController.findPetsByTags(tags);
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
| 400 | Invalid tag value | `ApiError` |

