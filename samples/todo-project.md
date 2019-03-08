---
description: this page contains sample of todo project configuration.
---

# Todo



### Todo project configuration <a id="todo-project-configuration"></a>

```text
 {
        "entities": [
            {
                "name": "person",
                "model": "Person",
                "table": "men",
                "fields": [
                    {
                        "title": "Id",
                        "name": "id",
                        "dbType": {
                            "type": "increments",
                            "primary": true
                        },
                        "viewType": {},
                        "searchable": false,
                        "sortable": true,
                        "fillable": false,
                        "inForm": false,
                        "inIndex": false
                    },
                    {
                        "title": "Name",
                        "name": "name",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "text"
                        },
                        "validations": "required",
                        "searchable": true,
                        "fillable": true,
                        "sortable": true,
                        "inForm": true,
                        "inIndex": true
                    },
                    {
                        "title": "Email",
                        "name": "email",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "email"
                        },
                        "validations": "required",
                        "searchable": false,
                        "fillable": true,
                        "sortable": true,
                        "inForm": true,
                        "inIndex": true
                    },
                    {
                        "title": "SMS",
                        "name": "sms",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "textarea"
                        },
                        "validations": "",
                        "searchable": false,
                        "fillable": true,
                        "inForm": true,
                        "inIndex": true
                    }
                ],
                "relations": [
                    {
                        "name": "Duties",
                        "type": "relation",
                        "relation": {
                            "type": "mtm",
                            "fieldView": "title",
                            "relatedEntity": "todo",
                            "middleEntity": "comment",
                            "pivotFields": [
                                "body"
                            ],
                            "foreignKey": "person_id",
                            "otherKey": "todo_id",
                            "localKey": "id"
                        },
                        "inForm": false,
                        "inView": true,
                        "inIndex": false
                    }
                ],
                "extraProperties": {
                    "softDelete": true,
                    "metable": true,
                    "cachable": true,
                    "sluggable": "name ,slug"
                },
                "generation": {
                    "model": true,
                    "createEvent": true,
                    "updateEvent": true,
                    "deleteEvent": true,
                    "listener": true,
                    "repository": true,
                    "createTable": true,
                    "createRequest": true,
                    "updateRequest": true,
                    "controller": true,
                    "route": true,
                    "breadcrumbs": true,
                    "lang": true,
                    "view": true,
                    "apiCreateRequest": true,
                    "apiUpdateRequest": true,
                    "apiController": true,
                    "apiRoute": true
                }
            },
            {
                "name": "todo",
                "model": "Todo",
                "table": "todos",
                "fields": [
                    {
                        "title": "Id",
                        "name": "id",
                        "dbType": {
                            "type": "increments",
                            "primary": true
                        },
                        "viewType": {},
                        "searchable": false,
                        "fillable": false,
                        "sortable": true,
                        "inForm": false,
                        "inIndex": false
                    },
                    {
                        "title": "Title",
                        "name": "title",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "text"
                        },
                        "validations": "",
                        "searchable": true,
                        "sortable": true,
                        "fillable": true,
                        "inForm": true,
                        "inIndex": true
                    },
                    {
                        "title": "Description",
                        "name": "description",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "textarea"
                        },
                        "validations": "",
                        "searchable": false,
                        "fillable": true,
                        "inForm": true,
                        "inIndex": true
                    },
                    {
                        "title": "Deadline",
                        "name": "deadline",
                        "dbType": {
                            "type": "date"
                        },
                        "viewType": {
                            "type": "date"
                        },
                        "validations": "required",
                        "searchable": true,
                        "fillable": true,
                        "sortable": true,
                        "inForm": true,
                        "inIndex": true
                    }
                ],
                "relations": [
                    {
                        "name": "Categories",
                        "type": "relation",
                        "relation": {
                            "type": "mtm",
                            "fieldView": "name",
                            "relatedEntity": "category",
                            "middleEntity": "todo category",
                            "pivotFields": [],
                            "foreignKey": "todo_id",
                            "otherKey": "category_id",
                            "localKey": "id"
                        },
                        "inForm": true,
                        "inView": true,
                        "inIndex": true
                    },
                    {
                        "name": "Users",
                        "type": "relation",
                        "relation": {
                            "type": "mtm",
                            "fieldView": "name",
                            "relatedEntity": "person",
                            "middleEntity": "comment",
                            "pivotFields": [
                                "body"
                            ],
                            "foreignKey": "todo_id",
                            "otherKey": "person_id",
                            "localKey": "id"
                        },
                        "inForm": false,
                        "inView": true,
                        "inIndex": false
                    }
                ],
                "extraProperties": {
                    "softDelete": true,
                    "metable": true,
                    "cachable": true,
                    "sluggable": "title ,slug"
                },
                "generation": {
                    "model": true,
                    "createEvent": true,
                    "updateEvent": true,
                    "deleteEvent": true,
                    "listener": true,
                    "repository": true,
                    "createTable": true,

                    "createRequest": true,
                    "updateRequest": true,
                    "controller": true,
                    "route": true,
                    "breadcrumbs": true,
                    "lang": true,
                    "view": true,
                    "apiCreateRequest": true,
                    "apiUpdateRequest": true,
                    "apiController": true,
                    "apiRoute": true
                }
            },
            {
                "name": "comment",
                "model": "Comment",
                "table": "comments",
                "fields": [
                    {
                        "title": "Id",
                        "name": "id",
                        "dbType": {
                            "type": "increments",
                            "primary": true
                        },
                        "viewType": {},
                        "searchable": false,
                        "fillable": false,
                        "inForm": false,
                        "sortable": true,
                        "inIndex": false
                    },
                    {
                        "title": "Body",
                        "name": "body",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "textarea"
                        },
                        "validations": "",
                        "searchable": false,
                        "fillable": true,
                        "inForm": true,
                        "inIndex": true
                    },
                    {
                        "title": "User Name",
                        "name": "person_id",
                        "dbType": {
                            "type": "Integer",
                            "foreign": {
                                "relatedEntity": "person",
                                "fieldView": "name",
                                "relatedField": "id"
                            }
                        },
                        "viewType": {
                            "type": "text"
                        },
                        "validations": "required",
                        "searchable": true,
                        "fillable": true,
                        "inForm": true,
                        "inIndex": true
                    },
                    {
                        "title": "Todo Title",
                        "name": "todo_id",
                        "dbType": {
                            "type": "Integer",
                            "foreign": {
                                "relatedEntity": "todo",
                                "fieldView": "title",
                                "relatedField": "id"
                            }
                        },
                        "viewType": {
                            "type": "text"
                        },
                        "validations": "required",
                        "searchable": true,
                        "fillable": true,
                        "inForm": true,
                        "inIndex": true
                    }
                ],
                "relations": [],
                "extraProperties": {
                    "softDelete": true,
                    "metable": true,
                    "cachable": true,
                    "sluggable": "body ,slug"
                },
                "generation": {
                    "model": true,
                    "createEvent": true,
                    "updateEvent": true,
                    "deleteEvent": true,
                    "listener": true,
                    "repository": true,
                    "createTable": true,

                    "createRequest": true,
                    "updateRequest": true,
                    "controller": true,
                    "route": true,
                    "breadcrumbs": true,
                    "lang": true,
                    "view": true,
                    "apiCreateRequest": true,
                    "apiUpdateRequest": true,
                    "apiController": true,
                    "apiRoute": true
                }
            },
            {
                "name": "category",
                "model": "Category",
                "table": "categories",
                "fields": [
                    {
                        "title": "Id",
                        "name": "id",
                        "dbType": {
                            "type": "increments",
                            "primary": true
                        },
                        "viewType": {},
                        "searchable": false,
                        "fillable": false,
                        "sortable": true,
                        "inForm": false,
                        "inIndex": false
                    },
                    {
                        "title": "Name",
                        "name": "name",
                        "dbType": {
                            "type": "string"
                        },
                        "viewType": {
                            "type": "text"
                        },
                        "validations": "required",
                        "searchable": true,
                        "fillable": true,
                        "sortable": true,
                        "inForm": true,
                        "inIndex": true
                    }
                ],
                "relations": [
                    {
                        "name": "Tasks",
                        "type": "relation",
                        "relation": {
                            "type": "mtm",
                            "fieldView": "title",
                            "relatedEntity": "todo",
                            "middleEntity": "todo category",
                            "pivotFields": [],
                            "foreignKey": "category_id",
                            "otherKey": "todo_id",
                            "localKey": "id"
                        },
                        "inForm": false,
                        "inView": true,
                        "inIndex": false
                    }
                ],
                "extraProperties": {
                    "softDelete": true,
                    "metable": true,
                    "cachable": true,
                    "sluggable": "name ,slug"
                },
                "generation": {
                    "model": true,
                    "createEvent": true,
                    "updateEvent": true,
                    "deleteEvent": true,
                    "listener": true,
                    "repository": true,
                    "createTable": true,

                    "createRequest": true,
                    "updateRequest": true,
                    "controller": true,
                    "route": true,
                    "breadcrumbs": true,
                    "lang": true,
                    "view": true,
                    "apiCreateRequest": true,
                    "apiUpdateRequest": true,
                    "apiController": true,
                    "apiRoute": true
                }
            }
        ]
    }
```

you can find todo project by Devyzer [here](https://github.com/devyzer/todo).

