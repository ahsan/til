# Get process running on a port
e.g port 3000
```
sudo lsof -t -i:3000
```

# Kill a process
```
kill <process number>
```
Running on a specific port:
```
sudo fuser -n tcp -k 3000
```
