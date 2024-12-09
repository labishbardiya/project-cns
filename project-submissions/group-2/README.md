# How to Run?

## First make sure the requirements from requirements.txt are installed. (Run in virtual env for better experience)

## Open build directory

### Run 'make'
This will automatically start the server.(Listening on port 12345) (Server IP can be updated in server.py)

### On the client side, client only needs the client.py file.
Run client.py on clients machine. (Make sure the server IP is correct)

## Execute the following commands on client side:

### Do the setup:
```bash
./setup <your_password> <logfilename>
```
### Now you can read and write entries in the logfile using your password.

#### Possible Commands:

```bash
./logappend -T <timestamp> -K <password> -A/-L -E <employee_name> logfile_name
./logappend -B batchfile_name
./logread -K <password> -S logfile_name
./logread -K <password> -T (-E <name> | -G <name>) logfile_name
./logread -K <password> -R (-E <name> | -G <name>) logfile_name
./logread -K <token> -I (-E <name> | -G <name>) [(-E <name> | -G <name>) ...] logfile_name
```

#### Some Examples:

```bash
./logappend -T 1 -K secret -A -E Alice log1
./logread -K secret -S log1
./logread -K secret -T -E John log1
./logread -K secret -R -E John log1
./logread -K secret -I -E John -G James log1
```

#### Available Flags:

logappend
```
    -T: Timestamp (required)
    -K: Password (required)
    -A/-L: Arrival or Departure
    -E/-G: Employee or Guest
    -R: Room ID (optional)
    -B: Batch file with commands (optional)
```
logread
```
    -K: Password (required)
    -S: Show campus state
    -R: List rooms visited
    -T: Calculate time spent
    -I: Shared room number
```
