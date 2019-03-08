---
description: this page describes the schema configurations of relation object.
---

# Relation

look to the following sample and relations:

![](../.gitbook/assets/relation-sample%20%281%29.PNG)

**mtm relation**:

```text
{
     "name": "name of relation ",
     "relation": {
          "type": "mtm",
          "fieldView": "view field in related entity",
          "relatedEntity": "related entity",
          "middleEntity": "middle entity",
          "pivotFields": [],
          "foreignKey": "foreign Key for current entity",
          "otherKey": "foreign Key for related entity"
     },
     "inForm": true,
     "inView": true,
     "inIndex": true
}
```



* without `pivotFields`

in this relation, the middle table doesn’t have any real data except foreign keys \(collection data\), and this entity doesn’t appear as an independent entity in a frontend, and its data added by the parent entity. such as `notifications` table in the previous example.

Example

```text
	{ 
         "name": "article",
         "model": "Article",
         "table": "articles",
         "fields": [{},{}],
         "relations": [
             {
                  "name": "get tags",
                  "type": "relation",
                  "relation": {
                       "type": "mtm",
                       "relatedEntity": "tag",
                       "fieldView":"type",
                       "middleEntity": "notification",
                       "pivotFields": [],
                       "foreignKey": "article_id",
                       "otherKey": "tag_id"          
                  },
                  "inForm": true,
                  "inView": true,
                  "inIndex": true
              }
            ]
        }
```



* with `pivotFields`

in this relation, the middle table has real data and foreign keys and this entity appears as an independent entity in a frontend, and its data added by Independent form such as `suggestions` table in the previous example.

Example

```text
	 {
         "name": "article",
         "model": "Article",
         "table": "articles",
         "fields": [{},{}],
         "relations": [
            {
               "name": "users",
               "type": "relation",
               "relation": {
                   "type": "mtm",
                    "relatedEntity": "user",
                    "fieldView":"name",
                    "middleEntity": "suggestion",
                    "pivotFields": ["rate"],
                    "foreignKey": "article_id",
                    "otherKey": "user_id"
                     },
               "inForm": false,
               "inView": true,
               "inIndex": false
            }
         ]
        }
```



**1tm relations**:

```text
		{
              "name": "name the relation ",
              "relation": {
                    "type": "1tm",
                    "relatedEntity": "related entity name",
                    "fieldView":"view field in related entity",
                    "foreignKey": "foreign Key for current entity"
              },
              "inForm": false,
              "inView": true,
              "inIndex": false
        }

```

Example

```text
	{ 
	    "name": "article",
	    "table": "articles",
        "fields": [],
        "relations": [
            {
              "name": "comments",
              "relation": {
                   "type": "1tm",
                   "relatedEntity": "comment",
                   "fieldView":"content",
                   "foreignKey": "article_id"
              },
        "inForm": false,
        "inView": true,
        "inIndex": false
          }
        ]
     }   
```

### mt1 relations: <a id="mt1"></a>

It is enough to define foreign keys fields.

```text
{
      "title": "field Name",
      "name": "field_id",
      "dbType": {
        "type": "Integer",
        "foreign": {
          "name":"name of relation",
          "relatedEntity": "related entity name",
          "fieldView": "view field in related entity"
          }
      },
      "viewType": {
        "type": "select"
      }
}
```

Example

```text
{
      "name": "comment",
      "fields": [
      {},{},
      {
           "title": "Article",
           "name": "article_id",
           "dbType": {
                 "type": "Integer",
                 "foreign": {
                       "name":"article",
                       "relatedEntity": "article",
                       "fieldView": "type"
                 }
           },
           "viewType": {
             "type": "select"
           },
           "validations": "required",
           "searchable": true,
           "fillable": true,
           "inForm": false,
           "inIndex": false
      }	
      ],
      "relations": []
}
```

