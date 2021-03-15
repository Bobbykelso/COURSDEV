/\*\* Zonne d'attente

-
-
- _//_

### **Dojo**

```javascript
const firstNames = ["Bob", "Jimmy", "Harry"];
const lastNames = ["Marley", "Hendrix", "Potter"];

function setFullName(i) {
  let fullName = firstNames[i] + " " + lastNames[i];
  return fullName;
}

const fullNameTab = [];

let i = 0;
while (firstNames[i]) {
  //!== false, undefined, null
  let fullName = setFullName(i);
  fullNameTab.push(setFullName(i));
  console.log(setFullName(i));
  i++;
}
```
