# ms4-gr43

## To build:
```
ant build-jar
```

## Start the external configuration service:
```
java -jar m4-ecs.jar
```

## Start server instances:
```
java -jar m4-server.jar -a localhost -p 30000 
java -jar m4-server.jar -a localhost -p 30001
...
```

## Start a client:
```
java -jar m4-client.jar
```
In the client CLI, type `help` to show a list of commands supported.

### Client command to connect to a server (e.g. the server listening on port 30000):
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
The user can type `rollback` during a transaction to abort.

### Sample commands to use the subscribe feature:
```
sub <regex_key>
unsub <regex_key>
```
```<regex_key>``` is the regular expression of keys to subscribe. 
For example, ```sub k.*``` subscribes to all keys starting with 'k'. 

Notification will be printed to the standard output.


### Command to reuse a previous command:
```
/<num_commands>
```
For example, ```/2``` would reuse the second last command that the user inputted.


