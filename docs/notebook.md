# Notebook

### Notebook Object
The notebook is the base resource in the application.

###### Notebook Structure
| Field        | Type    | Description                                                                                                                                                             |
|--------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| id           | unknown | The unique ID of this notebook object.                                                                                                                                  |
| name         | string  | A String containing the name displayed to the user in the application.                                                                                                  |
| permissions? | u2      | An unsigned two byte integer containing the permissions of the user (each bit represents a permission). Can be omitted if the user doesn't have access to the notebook. |
| owner        | boolean | Whether the user owns the notebook or not.                                                                                                                              |
| public       | boolean | Whether this notebook is publicly discoverable (i.e., no invite needed).    

## Get Current User Notebooks ``GET % /user/notebooks``
Returns a list of [notebook](#notebook-object) objects.
