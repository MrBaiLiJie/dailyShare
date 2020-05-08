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

## **随机打乱数组**

```
// Math.round() 函数返回一个数字四舍五入后最接近的整数。
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
		//生成一个随机正负数
		//排序
		arr.sort(() => {
			return Math.round(Math.random()) - 0.5;    //返回随机值（大于0|小于0）
		})
		console.log(arr);
```

```
  var Arr = [4,1,67,12,45,121,3];
		function randArr(arr) {
		    for (var i = 0; i < arr.length; i++) {
		        var iRand = parseInt(arr.length * Math.random());
		        var temp = arr[i];
		        arr[i] = arr[iRand];
		        arr[iRand] = temp;
		    }
		    return arr;
		}
		console.log(randArr(Arr));
```
