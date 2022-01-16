---

layout: default
title: "Pad"
description: "A pad is an object that holds user generated text."

---

# Pad

### Pad Object
A pad is an object that holds user generated text.

###### Pad Structure

| Field        | Type                 | Description                                                                                                                                                               |
|--------------|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| id           | string               | The unique ID of this collection object.                                                                                                                                  |
| name         | string               | A String containing the name displayed to the user in the application.                                                                                                    |
| permissions? | u16                  | An unsigned two byte integer containing the permissions of the user (each bit represents a permission). Can be omitted if the user doesn't have access to the collection. |                                                                                                                                                   |
| public       | boolean              | Whether this collection is publicly discoverable (i.e., no invite needed).                                                                                                |

###### Example Pad
```json
{
  "id": 8486878130674140662,
  "name": "Test Pad 1",
  "permissions": 0,
  "public": false
}
```

## HTTP Methods

### Get Content ``GET % /pads/{pad.id}/content``

Returns a content object:

| Field   | Type   | Description        |
|---------|--------|--------------------|
| title   | string | The pad's title.   |
| content | string | The pad's content. |
