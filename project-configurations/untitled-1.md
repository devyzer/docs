---
description: this page describes the schema configurations of field object.
---

# Field

You can distinguish between different types of fields and types:



**Id**:

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

**Integer**: 

```text
{
        
   "title": "Integer Value",
   "name": "field_name",
        "dbType": {
          "type": "Integer",
        },
        "viewType": {
          "type": "Integer"
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
            "name":"relation name"
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
              "value": "val1"
            },
            {
              "label": "Label Value2",
              "value": "val2"
            }
            {
            ....
            }
          ]
        },
      ....
      }
```

\*\*\*\*

**validations**:

required, max, min, unique,date and file :

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
* for more validations see [this](https://laravel.com/docs/5.7/validation#rule-same)

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

**in form**:

```text
  { 
    ....
    "inForm": "true",
    ....
   }
```

**in index**:

```text
  { 
    ....
   "inIndex": "true",
   ....
   }
```

**in view**:

```text
  { 
    ....
   "inView": "true",
   ....
   }      
```

**view type**:

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



