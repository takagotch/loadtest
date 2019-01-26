### loadtest
---
https://github.com/alexfernandez/loadtest

```js
const testserver = require('testserver');
const server = testserver.startServer({ port: 8000 });

const loadtest = require('loadtest');
function statusCallback(error, result, latency){
  console.log('Current latency %j, result %j, error %j', latency, result, error);
  console.log('----');
  console.log('Request elapsed milliseconds: ', result.requestElapsed);
  console.log('Request index: ', result.requestIndex);
  console.log('Request loadtest() instance index: ', result.instanceIndex);
}
const options = {
  url: 'http://localhost:8000',
  maxRequests: 1000,
  statusCallback: statusCallback
};
loadtest.loadTest(options, function(error){
  if(error){
    return console.error('Got an error: %s', error);
  }
  console.log('Test run successfully');
});

const loadtest = require('loadtest');
const options = {
  url: 'https://www.example.com',
  maxRequests: 100,
  secureProtocol: 'TLSv1_method'
};
loadtest.loadTest(options, function(error){
  if(error){
    return console.error('Got an error: %s', error);
  }
  console.log('Tests run successfully');
});

function(params, options, client, callback){
  generateMessageAsync(function(message)){
    request = client(options, callback);
    if(message)
    {
      optoins.headers['Content-Length'] = message.length;
      options.headers['Content-Type'] = 'application/x-www-form-urlencoded';
      request.write(message);
    }
    request.end();
  }
}

const loadtest = require('loadtest');
const options = {
  url: 'http://localhost:8000',
  maxRequests: 1000,
};
loadtest.loadTest(options, function(error, result)
{
  if(error)
  {
    return console.error('Got an error: %s', error);
  }
  console.log('Tests run successfully');
});

module.exports = function(params, options, client, callback){
  generateMessageAsync(function(message){
    if(message)
    {
      options.headers['Content-Length'] = message.length;
      options.headers['content-Type'] = 'application/x-www-form-urlencoded';
    }
    request = client(options, callback);
    if(message){
      request.write(message);
    }
    return request;
  })
}

module.exports = function(requestId){
  return {
    key: 'value',
    requestId: requestId
  };
};
```


```
{
  totalRequests: 1000,
  percentiles: {
    '50': 7,
    '90': 10,
    '95': 11,
    '99': 15
  },
  rps: 2824,
  totalTimeSeconds: 0.354108,
  meanLatencyMs: 7.72,
  maxLatencyMs: 20,
  totalErrors: 3,
  errors: {
    '0': 1,
    '500': 2
  }
}

{
  host: 'localhost',
  path: '/',
  method: 'GET',
  statusCode: 200,
  body: '<html><body>hi</body></html>',
  headers: [...]
}

{
  acceot: "text/plain;text/html"
}

```

```
loadtest http://localhost:7357/ -t 20 -c 10 -k
loadtest http://localhost:7357/ -t 20 -c 1- --keeplive --rps 2000

npm install -g loadtest
sudo npm install -g loadtest

loadtest [-n requests] [-c concurrency] [-k] URL
loadtest
loadtest -c 10 --rpc 200 http://mysite.com
loadtest -H user-agent:tester/0.4
loadtest -H accept:text/plain;text-html ...
loadtest -H "authorization: Basic xxx=="
loadtest <url> -c 10 --rps 10
testserver-loadtest [--delay ms] [error 5xx] [percent yy] [port]
sudo npm install -g loadtest
testserver-loadtest
loadtest http://localhost:7357/ -t 20 -c 10
```


