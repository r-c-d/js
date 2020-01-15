# Javascript Snippets


## Iterating through a JSON object with nested keys
```javascript
<!DOCTYPE html>
<html>
<body>

<p>Looping through arrays inside arrays.</p>

<p id="demo"></p>

<script>
var myObj, x = "";
myObj = {
  "resno": "X0000",
  "e_mail": "s.mann@smann.com",
  "balances": {
    "vac": "416",
    "med": "802",
    "com":"100"
  },
  "gsID": "some string value"
}


Object.keys(myObj).forEach(key => {
    if(typeof (myObj[key]) !== 'object'){
    	x += key + ":" + myObj[key] + " ";
    } else{
    	var nestedObj = myObj[key];
        Object.keys(nestedObj).forEach(key => {
        	x += key + ":" + nestedObj[key] + " ";
        })
    }
  });

document.getElementById("demo").innerHTML = x;
</script>

</body>
</html>

```
