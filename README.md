## **随机抽奖程序：思路一**

**接收一个数组，从数组中抽出 n 个人。**
**简单的抽奖的做法，是把号码写到一个球上面，摇 n 次，然后每次摇出 1 个号，该号码即为中奖号码，同时将该号码拿出去，重复 n 次。**

```
  window.onload = function load(){
    	const arr = [1,8,6,17,22,99];
    	const n = 6;
    	draw(arr,n);
     };
       function draw(arr,n){
    		// alert(n)
    		const result = [];
    		let i = 0;
    		while(i < n ){
    			// alert(111)
    			const value = arr.splice(Math.floor(Math.random()*arr.length),1);
    			result.push(value[0]);
    			i++;
    		}
    		return result
    	}
```
