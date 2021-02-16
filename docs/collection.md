# Collection

### Collection Object
The collection is the base resource in the application.

###### Collection Structure

| Field        | Type                 | Description                                                                                                                                                               |
|--------------|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| id           | unknown              | The unique ID of this collection object.                                                                                                                                  |
| name         | string               | A String containing the name displayed to the user in the application.                                                                                                    |
| permissions? | u16                  | An unsigned two byte integer containing the permissions of the user (each bit represents a permission). Can be omitted if the user doesn't have access to the collection. |
| pads         | array of pad objects | The pads in the collection.                                                                                                                                               |
| owner        | unknown              | The ID of the owner                                                                                                                                                       |
| public       | boolean              | Whether this collection is publicly discoverable (i.e., no invite needed). 

###### Example Collection
```json
{
  "id" : "722608120345657365",
  "name" : "An Example Pad",
  "permissions" : 1
  "pads" : [
    {
      "id" : "722823252396736572",
      "name" : "Example Pad 1",
      "permissions" : 1,
      "owner" : "722823252396736572",
      "public" : false
    },
    {
      "id" : "722823213863796766",
      "name" : "Example Pad 2",
      "permissions" : 1,
      "owner" : "722823252396736572",
      "public" : false
    }
  ]
  "owner" : "300383967121768459",
  "public" : true
}
```

---

## HTTP Methods

### Get Current User Collections ``GET % /user/notebooks``
Returns an array of [collection](#collection-object) objects.


### Create Collection ``POST % /collections/new``

Creates a new collection. Returns a [collection](#collection-object) object on success.

###### JSON Params

| Field  | Type    | Description                                                                |
|--------|---------|----------------------------------------------------------------------------|
| name   | string  | A String containing the name displayed to the user in the application.     |
| public | boolean | Whether this collection is publicly discoverable (i.e., no invite needed). |


### Get Collection Pads ``GET % /collections/{collection.id}/pads``
Returns an array of pad objects on success.

### Create New Pad ``POST % /collections/{collection.id}/pads/new``
Returns the pad object on success.
