# speedjs
Speed comparisons

### Routing loop
Which is faster  
``` javascript
let routesMap = {};
for (const route of routes) {
    let key = route["ser"] + ':' + route["action"];
    routesMap[key] = route["handler"];
}
connection.socket.on('message', async req => {
let ___req = req;
let ___reqKey = ___req.ser + ':' + ___req.action;
if (___reqKey in routesMap) {
   ___res = await routesMap[___reqKey](req);
   console.log(JSON.stringify(___res));
}
}
```
or
``` javascript
connection.socket.on('message', async req => {
let ___req = req;
for (const route of routes) {
       if (route.ser == ___req.ser && route.action == ___req.action) {
                ___res = await route.handler(req);
                break;
            }
}
}
```

Author: Zero Profit
