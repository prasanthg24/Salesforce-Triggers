# Salesforce-Triggers

<h1>Salesforce Trigger Concepts </h1>

<h2> Types of Triggers </h2>

1.Before Trigger
2.After Trigger

Trigger context variable
isExecuting
isInsert
isUpdate
isDelete
isBefore
isAfter
isUndelete
new
newMap
old
oldMap
size

<h6>
List of all Trigger Context Variables 
Trigger.isExecuting: Returns true if the current context for the Apex code is a trigger, not a Visualforce page, a Web service, or an executeanonymous() API call.
Trigger.isInsert: Returns true if this trigger was fired due to an insert operation, from the Salesforce user interface, Apex, or the API.
Trigger.isUpdate: Returns true if this trigger was fired due to an update operation, from the Salesforce user interface, Apex, or the API.
Trigger.isDelete: Returns true if this trigger was fired due to a delete operation, from the Salesforce user interface, Apex, or the API.
Trigger.isBefore: Returns true if this trigger was fired before any record was saved.
Trigger.isAfter: Returns true if this trigger was fired after all records were saved.
Trigger.isUndelete: Returns true if this trigger was fired after a record is recovered from the Recycle Bin (that is, after an undelete operation from the Salesforce user interface, Apex, or the API.)
Trigger.new: Returns a list of the new versions of the sObject records. This sObject list is only available in insert, update, and undelete triggers, and the records can only be modified in before triggers.
Trigger.newMap: A map of IDs to the new versions of the sObject records. This map is only available in before update, after insert, after update, and after undelete triggers.
Trigger.old : Returns a list of the old versions of the sObject records. This sObject list is only available in update and delete triggers.
Trigger.oldMap: A map of IDs to the old versions of the sObject records. This map is only available in update and delete triggers.
Trigger.size: The total number of records in a trigger invocation, both old and new.
</h6>

Trigger Context Variables Considerations
trigger.new and trigger.old cannot be used in Apex DML operations.
You can use an object to change its own field values using trigger.new, but only in before triggers. In all after triggers, trigger.new is not saved, so a runtime exception is thrown.
trigger.old is always read-only.
You cannot delete trigger.new.
