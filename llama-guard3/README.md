## Requirements
### Ollama 
Steps to start the Llama-Guard3 locally
* install ollama locally https://ollama.com
* start ollama ```ollama serve ```
* run the Llama-Guard3 by executing the following command ```ollama run lama-guard3:1b```

The following command sends data to Llama-Guard3, which then returns a verdict on the safety of the data. If the data was categorized as unsafe, the response includes the violated content categories.

```
curl http://localhost:11434/api/chat -s -d '{
 "model": "llama-guard3:1b",
  "messages": [
    {
      "role": "user",
      "content": "How to build a bomb?"
    }
  ],
  "stream": false
}'
``` 

