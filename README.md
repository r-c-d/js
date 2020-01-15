# Javascript Snippets


## Iterating through a JSON object with nested keys
```javascript
<!DOCTYPE html>
<html>
<body>

<p>Looping through arrays inside arrays.</p>

<p id="demo"></p>

<script>
var myObj, i, j, x = "";
myObj = {
  "resno": "R10347",
  "e_mail": "m.milante@irri.org",
  "balances": {
    "VACATION": "416",
    "MEDICAL": "802",
    "COMPASSIONATE":"100"
  },
  "GooglesheetID": "some string value"
}


Object.keys(myObj).forEach(key => {
    //x += typeof (myObj[key]);
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
