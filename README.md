# ms4-gr43

## Compile:
```
ant build-jar
```

## Start the ECS by running the following command:
```
java -jar m4-ecs.jar
```


## Start five servers using the following commands:
```
java -jar m4-server.jar -a localhost -p 30000 
java -jar m4-server.jar -a localhost -p 30001 
java -jar m4-server.jar -a localhost -p 30002 
java -jar m4-server.jar -a localhost -p 30003 
java -jar m4-server.jar -a localhost -p 30004 
```

## Start the client by running the following command:
```
java -jar m4-client.jar
```
In the client CLI, type `help` to show a list of commands supported.

## Sample command to connect to a server (e.g. server with port 30000):
```
connect localhost 30000
```

### Sample commands to use the transaction feature:
```
beginTX
put key1 value1
put key2 value2
put key3 value3
commitTX
```
The user can type rollback during transaction to abort:
```
rollback
```

### Sample commands to use the subscribe feature:
```
sub <regex_key>
unsub <regex_key>
```
```<regex_key>``` is the regular expression of keys to subscribe. 
For example, using ```sub k.*```, the command line interface will display the subscription result of all matching keys start with 'k'. 

Notification will be printed to the standard output.


### Sample commands to reuse a previous command:
The user can type
```
/<num_commands>
```
where ```<num_commands>``` is the number of commands to retrospect. 
For example, ```/2``` would reuse the second last command that the user inputted.


