---
description: this page describes the schema configurations of entity object.
---

# Entity

**Entities**: 

every entity contains the following attributes:

* name:  entity name.
* model: model name.
* table:table name.
* briefTitle:  entity title.
* fields: entity fields.
* relations:entity relations.
* extraProperties: detecting other properties such as: softDelete, metable ...etc.
* generation: can detect files that Devyzer will generate them.
* inherit: can inheriting entity from snippets.



_**Fields**_ : 

every field contains the following attributes:

* title: field title
* name: field name
* dbType: contains the following attributes: 
  * type: one of these [types](https://www.tkserver.com/laravel-database-column-types).
  * primary: is primary or not.
  * default: a default value
  * foreign: if this field is a foreign, must detect  the following attributes: 
    * name: name of relation.
    * relatedEntity: name of related entity
    *  fieldView: the field that you want to view it in the related entity.
* viewType: contains the following attributes:
  *  type : one of  `Integer`,`text`,`textarea`,`password`,`hidden`, `date`, `select`, `ckeditor` , `token`, `Image`
  *  enums: if this field is an enum, must detect a list of the following attributes: 
    * label.
    * value. 
* searchable: specifies whether the field is searchable or not.
* fillable: specifies whether the field is fillable or not.
* sortable: specifies whether the field is sortable or not.
* inForm: specifies whether the field is an input field or not.
* inIndex: specifies whether the field will appear in index page \(list\) or not.
* inView: specifies whether the field will appear in view page or not.



_**Relations**_: 

every relation contains the following attributes:

* name: relation name
* relation: contains the following attributes: 
  * type: `mtm`, `1tm`.
  * relatedEntity: name of the related entity.
  * middleEntity : name of the middle entity
  * pivotFields : array of middle entity fields.
  * fieldView: the field that you want to view it in the related entity
  * foreignKey: name of foreign Key field for current entity.
  * otherKey: name of foreign Key field for related entity.
* inForm: specifies whether the relation is input  or not.
* inIndex: specifies whether the relation will appear in list page or not.
* inView: specifies whether the relation will appear in view page or not.



_**Extra Properties**:_  

contains the following attributes:

* softdelete: `true`, `false`
* metable: `true`, `false`
* cachable: `true`, `false`
* timestamp: `true`, `false`
* sluggable: `field name`,`slug` or `null` 



_**Generation**_: 

 every attribute in generation detect if Devyzer will generate  appropriate file or not, and it contains the following attributes:

* model : `true`, `false`
* createEvent : `true`, `false`
* updateEvent : `true`, `false`
* deleteEvent : `true`, `false`
* listener : `true`, `false`
* repository : `true`, `false`
* createTable : `true`, `false`
* createRequest : `true`, `false`
* updateRequest : `true`, `false`
* controller : `true`, `false`
* route : `true`, `false`
* breadcrumbs : `true`, `false`
* lang : `true`, `false`
* view : `true`, `false`
* apiCreateRequest : `true`, `false`
* apiUpdateRequest : `true`, `false`
* apiController : `true`, `false`
* apiRoute : `true`, `false`  



