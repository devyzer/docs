---
description: This page describes the schema configurations of the field object.
---

# Field

You can distinguish between the different types of fields and types:

**id**:

```text
{
  "title": "Id",
  "name": "id",
  "dbType": {
    "type": "increments",
    "primary": true
   }
},

```

**integer**: 

```text
{
        
   "title": "Integer Value",
   "name": "field_name",
        "dbType": {
          "type": "integer",
        },
        "viewType": {
          "type": "integer"
        },
}

```

**double**:

```text
{
    "title": "Double Value",
    "name": "field_name",
    "dbType": {
      "type": "double",
    },
    "viewType": {
      "type": "decimal",
    },
  }
```

**default**:

```text
{   
    .........
    "dbType": {
      "type": "...",
      "default": "default value"
    },
    "viewType": {
     ..........
    },
   ............
 }
```

**foreign**:

```text
 	{
      "title": "field Name",
      "name": "field_id",
      "dbType": {
        "type": "Integer",
        "foreign": {
            "name": "relation name"
            "relatedEntity": "related entity name",
            "fieldView": "field_name",
         ...
        }
      },
      "viewType": {
        "type": "select"
      },
    .....
    }
```

**enum**:

```text
   {
     ....
        "dbType": {
          "type": "enum"
        },
        "viewType": {
            "type": "select",
          "enums": [
            {
              "label": "Label Value1",
              "value": "value1"
            },
            {
              "label": "Label Value2",
              "value": "value2"
            }
            {
            ....
            }
          ]
        },
      ....
      }
```

**validations**:

Available options are: required, max, min, unique, date and file

* ```text
  "validations": "required|...", 
  ```
* ```text
  "validations": "max:max_value|...",
  ```
* ```text
  "validations": "min:min_value|...",
  ```
* ```text
  "validations": "unique:tabel_name|...",
  ```
* ```text
  "validations": "date|...",
  ```
* ```text
  "validations": "file|...",
  ```

_For more validations, check_ [_this link_](https://laravel.com/docs/5.7/validation#rule-same)\_\_

**searchable**:

```text
  { 
    ....
    "searchable": "true",
    ....
   }
```

**sortable**:

```text
  { 
    ....
    "sortable": "true",
    ....
   }
```

**fillable**:

```text
  { 
    ....
    "fillable": "true",
    ....
   }
```

**inForm**:

```text
  { 
    ....
    "inForm": "true",
    ....
   }
```

**inIndex**:

```text
  { 
    ....
   "inIndex": "true",
   ....
   }
```

**inView**:

```text
  { 
    ....
   "inView": "true",
   ....
   }      
```

**viewType**:

* ```text
  "viewType": {
     "type": "text"
  }
  ```
* ```text
  "viewType": {
     "type": "textarea"
  }
  ```
* ```text
  "viewType": {
     "type": "password"
  }
  ```
* ```text
  "viewType": {
     "type": "hidden"
  }
  ```
* ```text
  "viewType": {
     "type": "email"
  }
  ```
* ```text
  "viewType": {
     "type": "date"
  }
  ```
* ```text
  "viewType": {
     "type": "select"
  }
  ```
* ```text
  "viewType": {
     "type": "ckeditor"
  }
  ```
* ```text
  "viewType": {
     "type": "token"
  }
  ```
* ```text
  "viewType": {
     "type": "img"
  },
  ```



