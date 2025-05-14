The docker-compose file starts two services
* presidio-analyzer is avaiable on the port 5002
* residio-anonymizer is listening on port 5001

To start it execute the following command
```
docker-compose up
```
Use the next command to send the data to the analyzer on port 5002

```
curl -X POST http://localhost:5002/analyze -d '{"text":"Dieter Bohlen email address is d.bohlen@fake.com", "language":"en"}' --header "Content-Type: application/json"
```
Save the response from the analyzer in a json file e.g. _analyzed.json_
```
{
  "text":"Dieter Bohlen email address is d.bohlen@fake.com",
  "analyzer_results": PUT_RESPONSE_DATA_HERE
}
``` 

Next, post the analyzed.json file (or use the existing response.json file) to the presidio anonymizer listening on port 5001. You can utilize the following command
. 
```
curl -i -X POST http://localhost:5001/anonymize -d @analyzed.json --header "Content-Type: application/json"
```
