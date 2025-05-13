The docker-compose file starts two components 
* presidio-analyzer avaiable on the port 5002
* residio-anonymizer listening on port 5001

To start it execute the following command
```
docker-compose up
```
Use the command to send it to the analyzer

```
curl -X POST http://localhost:5002/analyze -d '{"text":"John Smith drivers license is AC432223", "language":"en"}' --header "Content-Type: application/json"
```

