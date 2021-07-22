# speedjs
Speed comparisons

### Routing loop
Which is faster  
``` javascript
if (___reqKey in routesMap) {
   ___res = await routesMap[___reqKey](req);
   console.log(JSON.stringify(___res));
}
```
or
``` javascript
for (const route of routes) {
       if (route.ser == ___req.ser && route.action == ___req.action) {
                ___res = await route.handler(req);
                break;
            }
}
```

Author: Zero Profit
