# COMP23111 Database System 

## Trigger

### MySQL Triggers

A trigger is a stored program that is invoked automatically in response to an event   

- Triggers are run BEFORE or AFTER the SQL query is executed

- Triggers provide another way to check the integrity of data

- Triggers can be used to run scheduled tasks 

- Triggers are often used for auditing data changes in tables

- The events are: INSERT, UPDATE and DELETE 

  ### Showing and Dropping trigger

  #### To show a trigger 

  ```mysql
  SHOW TRIGGERS;
  ```

  #### To drop a trigger 

  ```mysql
  DROP TRIGGER trigger_name;
  ```

  #### Creating a Trigger 

  ```mysql
  CREATE TRIGGER trigger_name
  BEFORE|AFTER
  INSERT|UPDATE|DELETE
  ON table_name
  BEGIN 
  	trigger_body
  END	
  ```

  #### NEW and OLD modifiers

  To distinguish between the old data and the new data we have NEW and OLD modifiers

  

  ###  

  