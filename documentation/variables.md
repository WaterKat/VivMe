# Variables
VivMe allows plugins to interact with variables. These variables themselves can be used as inputs for configurations, as well as other plugins. Using the "$" identifier, you can use the variable id to supplement a value for a variable. 

```json
{
    "variables": {
        "mouth_open": "0.0",
        "smile": "0.0",
    }
}
```

In the example sprite information 
```json
{ 
    "name": "circle",
    "parent": "global",
    "transform": {
        "matrix": [
                0, "$mouth_open", 0, 0,
                "$smile", 0, 0, 0,
                0, 0, 0, 0,
                0, 0, 0, 0
            ] 
    }, 
... 
}
```
"mouth_open" and "smile" are later replaced by the value of these variables