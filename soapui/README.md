# [SoapUI](https://www.soapui.org/)

## Groovy scripts

### REST request query parameters (source: self)

<sup>25-03-2022, source: self</sup>

```groovy
def queryString = mockRequest.getRequest().getQueryString();
log.info "queryString: " + queryString;

Map queryParametersMap = [:]
if (queryString != null) {
    String[] queryParameters = queryString.split("&")
    for (queryParameter in queryParameters) {
        String[] keyValue = queryParameter.split("=")
        queryParametersMap[keyValue[0]] = keyValue[1]
    }
}

def whatever = queryParametersMap["whatever"];
```

### REST PUT and DELETE request body

<sup>25-03-2022, source: unknown + self</sup>

```groovy
mockRequest.with {
    if (method.toString() == 'PUT' || method.toString() == 'DELETE') {
        BufferedReader br = new BufferedReader(new InputStreamReader(request.getInputStream(), "UTF-8"));
        StringBuilder sb = new StringBuilder()
        while ((s=br.readLine())!=null) { 
            sb.append(s)
        }

        def requestBody = new groovy.json.JsonSlurper().parseText(sb.toString())
        log.info "requestBody: " + requestBody
        
        def whatever = requestBody.whatever;
    }
}
```
