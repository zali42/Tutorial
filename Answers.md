# TEAM 10

## Members: Marilla Livingston, Jennea Kaye Fiestan, Andrew Merrick, Zuhur Ali

What makes an item unique in a table with a composite primary key?

An item is made unique by the combination of its partition key and sort key. Even if two items share the same partition key, they must have different sort keys, so the complete composite primary key uniquely identifies each item.

Which key condition retrieves the registrations for one training event?

Use Pk = "EVENT#TR001" and SK that starts with "REGISTRATION#." To get all registration for training event TRN001

Why does a filtered Scan still evaluate items?

DynamoDB checks the item first then applies the filter the filter shows fewer results, but DynamoDB still does the same amount of reading.  

What evidence would justify proposing a secondary index?

A secondary index would be justified when a required search cannot use the table's existing PK and SK efficiently if the search checks many items but returns only a few matches an index could make it faster and reduce costs.  

What does LastEvaluatedKey tell the Boto3 caller?

The  LastEvaluatedKey shows where DynamoDB stopped reading, use it as ExclusiveStartKey in the next request to continue if it is missing or empty, you have reached the end.  

What is one modeling decision you changed after testing the access patterns?

When changed the keys so registration for the same event share a partition key, while each registration has a different sort key this helped us get one event's registrations using a Query.

Our modelling decision was to add a GSI using the composite key as the new PK and the status as the SK.
