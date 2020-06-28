## **循环遍历数组:**

```
var array = ["山东","山西","河南","陕西","安徽",];
var newArray = "";
for (var i = 0; i < array.length; i++) {
    newArray += array[i] + ""
  }
console.log(newArray)   //山东山西河南陕西安徽
```

## **遍历二维数组:**

```
// 遍历二维数组
 var array = [["山东","山西"],["河南","陕西"],["安徽","江苏"]]
 var newArray = "";
 for (var i = 0; i < array.length; i++) {
      for (var j = 0; j < array[i].length; j++) {
         newArray += array[i][j] + ""
   }
 }
 console.log(newArray)    //山东山西河南陕西安徽江苏
```

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

## **随机打乱数组:**

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
## **日期转化:**
```
 // 日期转化
    dateFormat(fmt, date) {
      let ret;
      const opt = {
        "y+": date.getFullYear().toString(), // 年
        "M+": (date.getMonth() + 1).toString(), // 月
        "d+": date.getDate().toString() // 日
        // 有其他格式化字符需求可以继续添加，必须转化成字符串
      };
      for (let k in opt) {
        ret = new RegExp("(" + k + ")").exec(fmt);
        if (ret) {
          fmt = fmt.replace(
            ret[1],
            ret[1].length == 1 ? opt[k] : opt[k].padStart(ret[1].length, "0")
          );
        }
        this.productionDate = fmt;
      }
      return fmt;
    },
    
    // 调用的时候传值
    this.dateFormat("yyyy-MM-dd", '值');
    
    ```