```
循环遍历数组:
var array = ["山东","山西","河南","陕西","安徽",];
var newArray = "";
for (var i = 0; i < array.length; i++) {
    newArray += array[i] + ""
  }
console.log(newArray)   //山东山西河南陕西安徽
遍历二维数组:
// 遍历二维数组
 var array = [["山东","山西"],["河南","陕西"],["安徽","江苏"]]
 var newArray = "";
 for (var i = 0; i < array.length; i++) {
      for (var j = 0; j < array[i].length; j++) {
         newArray += array[i][j] + ""
   }
 }
 console.log(newArray)    //山东山西河南陕西安徽江苏
随机抽奖程序：思路一
接收一个数组，从数组中抽出 n 个人。 简单的抽奖的做法，是把号码写到一个球上面，摇 n 次，然后每次摇出 1 个号，该号码即为中奖号码，同时将该号码拿出去，重复 n 次。

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
随机打乱数组:
// Math.round() 函数返回一个数字四舍五入后最接近的整数。
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
		//生成一个随机正负数
		//排序
		arr.sort(() => {
			return Math.round(Math.random()) - 0.5;    //返回随机值（大于0|小于0）
		})
		console.log(arr);
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
判断数组中是否所有项都满足某条件 :
// 判断条件：所有的水果都必须是红色
	const fruits = [
	{ name: 'apple', color: 'red' },
	{ name: 'banana', color: 'yellow' },
	{ name: 'grape', color: 'purple' }
	];
     judge();

	1.// function judge() {
	// 	let allFruitsRed = true;
	// 	for (let f of fruits) {
	// 		allFruitsRed = (f.color === 'red');
 //            if (!allFruitsRed) break;
	// 	}
	// 	console.log(allFruitsRed)    // false
	// };

     2.// 使用 Array.every
     // every() 方法用于检测数组所有元素是否都符合指定条件（通过函数提供）。
     // every() 方法使用指定函数检测数组中的所有元素：
     // 如果数组中检测到有一个元素不满足，则整个表达式返回 false ，且剩余的元素不会再进行检测。
     // 如果所有元素都满足条件，则返回 true。
     // 注意： every() 不会对空数组进行检测。
     // 注意： every() 不会改变原始数组。
     function judge() {
		let allFruitsRed = true;
			for (let f of fruits) {
			allFruitsRed = fruits.every(f => f.color == 'red')
		}
		console.log(allFruitsRed)  // false

	};
判断数组中是否有某一项满足条件:
 // 判断条件：所有的水果中有一项是红色
	const fruits = [
	{ name: 'apple', color: 'red' },
	{ name: 'banana', color: 'yellow' },
	{ name: 'grape', color: 'purple' }
	];
    judge();
   // some() 方法用于检测数组中的元素是否满足指定条件（函数提供）。
   // some() 方法会依次执行数组的每个元素：
   // 如果有一个元素满足条件，则表达式返回true , 剩余的元素不会再执行检测。
   // 如果没有满足条件的元素，则返回false。
   // 注意： some() 不会对空数组进行检测。
   // 注意： some() 不会改变原始数组。
	function judge() {
		let allFruitsRed = true;
			for (let f of fruits) {
			allFruitsRed = fruits.some(f => f.color == 'red')
		}
		console.log(allFruitsRed)   //true

	};
查找第一个符合条件的数组元素:
// find()方法用于查找第一个符合条件的数组元素.它的参数是一个回调函数。在回调函数中可以写你要查找元素的条件，当条件成立为true时，返回该元素。如果没有符合条件的元素，返回值为undefined。
//注意: find() 对于空数组，函数是不会执行的。
//注意: find() 并没有改变数组的原始值。
  const fruits = [
	{ name: 'apple', color: 'red',num:1 },
	{ name: 'banana', color: 'yellow',num:2 },
	{ name: 'grape', color: 'purple',num:3 },
  { name: 'orange', color: 'purple',num:3 }
	];
	const arr = [1,2,3,4,5,6,7];
  //以下代码在arr数组中查找元素值大于1的元素，找到后立即返回。返回的结果为查找到的元素：
  var resultArr = arr.find(f => f >1);
  console.log(resultArr)  // 2
  //没有符合元素，返回undefined:
  var resultArr = arr.find(f => f >8);
  console.log(resultArr)  // undefined
  // 回调函数有三个参数。value：当前的数组元素。index：当前索引值。fruits：被查找的数组。
 // 查找索引值为2的元素：
	var result = fruits.find((value,index,fruits) => {
		return index == 2
	});
	console.log(result)  // {name: "grape", color: "purple", num: 3}

findIndex()
findIndex()与find()的使用方法相同，只是当条件为true时findIndex()返回的是索引值，而find()返回的是元素。如果没有符合条件元素时findIndex()返回的是-1，而find()返回的是undefined。findIndex()当中的回调函数也是接收三个参数，与find()相同。
  var resultArr = fruits.findIndex(f => f.num == 3);
  console.log(resultArr)  // 2
  var resultArr = fruits.findIndex(f => f.num == 8);
  console.log(resultArr)  // -1
Array 其他方法
 1.array.filter()
 filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。
 注意： filter() 不会对空数组进行检测。
 注意： filter() 不会改变原始数组。
 	const fruits = [
	{ name: 'apple', color: 'red',num:1 },
	{ name: 'banana', color: 'yellow',num:2 },
	{ name: 'grape', color: 'purple',num:3 },
	{ name: 'orange', color: 'purple',num:3 }
	];
	const arr = [1,2,3,4,5,6,7];
  const resultArr = fruits.filter(f => f.num >2);
  console.log(resultArr)  // 返回指定数组中符合条件的所有元素。
  // 0: {name: "grape", color: "purple", num: 3}1: {name: "orange", color: "purple", num: 3}

  2.array.join()
  join()方法用于把数组中的所有元素转换一个字符串。
  元素是通过制定的分隔符进行分割的。
  const arr = [1,2,3,4,5,6,7];
  const resultArr = arr.join('and');
  console.log(resultArr)   // 1and2and3and4and5and6and7
  3.array.reverse()
  reverse() 方法用于颠倒数组中元素的顺序。
  const arr = [1,2,3,4,5,6,7];
  const resultArr = arr.reverse();
  console.log(resultArr)   //[7, 6, 5, 4, 3, 2, 1]
日期转化:
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


判断浏览器类型:
browserType:function(){
  var browser = window.navigator.userAgent; *//获取浏览器*
  if (userAgent.indexOf("Opera") > -1)
      { return "Opera" }; *//判断是否Opera浏览器*
  if (userAgent.indexOf("Firefox") > -1)
      { return "FireFox";  } *//判断是否Firefox浏览器*
  if (userAgent.indexOf("Chrome") > -1)
      {  return "Chrome";  }  *//判断是否chrome浏览器*
  if (userAgent.indexOf("Safari") > -1)
      { return "Safari"; } *//判断是否Safari浏览器* •
  if (userAgent.indexOf("compatible") > -1 && userAgent.indexOf("MSIE") > -1 && !isOpera)
      {  return "IE";  }; *//判断是否IE浏览器* }
获取当前浏览器是 ie 几 :
function IEVersion(newsVsesion) {
    // console.log(111)
    var userAgent = navigator.userAgent; //取得浏览器的userAgent字符串
    var isIE = userAgent.indexOf("compatible") > -1 && userAgent.indexOf("MSIE") > -1; //判断是否IE<11浏览器
    var isEdge = userAgent.indexOf("Edge") > -1 && !isIE; //判断是否IE的Edge浏览器
    var isIE11 = userAgent.indexOf('Trident') > -1 && userAgent.indexOf("rv:11.0") > -1;
    if(isIE) {
        var reIE = new RegExp("MSIE (\\d+\\.\\d+);");
        reIE.test(userAgent);
        var newsVsesion = parseFloat(RegExp["$1"]);
        // console.log(newsVsesion)
    }
    else{
    }
};
```