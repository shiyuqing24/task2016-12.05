hello、
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<pre>
    获取页面中所有标签的种类

    tagName 获取元素标签名
</pre>
<pre>
    1
</pre>
<script>
    /*第一种*/
    var doms=document.getElementsByTagName("*");
    console.log('doms',doms);

    /*第二种*/
    var doms1=document.querySelectorAll("*");
    console.log('doms1',doms1);

    /*第三种 对象转换成数组*/
    var domArr=Array.from(doms1);
    console.log('domArr',domArr);
    console.log('domArr.slice',domArr.slice());

    /*自定义方法*/
    function objToArr(obj){
        var arr=[];
        var i,
                lg=obj.length;
        for(var i=0;i<lg;i++){
            arr.push(obj[i]);
        }
        return arr;
    }
    var toDoms1=objToArr(doms1)
    console.log("toDoms1",toDoms1);


    /*返回dom元素标签名的数组*/

    function  domByTagName(dArr){
        var tagArr=[];
        var i,lg=dArr.length;
        for(i=0;i<lg;i++){
            tagArr.push(dArr[i].tagName);
            }
        return tagArr;
    }
    /*获取由标签名组成的新数组*/
    var tagNameArr=domByTagName(domArr);
    console.log('tagNameArr',tagNameArr);
    var newArr=[];
    /*去除重复*/
  for(var i=0;i<tagNameArr.length;i++){
      if(newArr.indexOf(tagNameArr[i])==-1){
       newArr.push(tagNameArr[i])
      }
  }
    console.log('newArr',newArr)

/*另一种去除重复*/
    function uArr(arr){
        var i,
                lg=arr.length;
        var newArr=[];
        for(var i=0;i<lg;i++){
            for(var j=0;j<i.length;j++){
                if(arr[i]!=newArr[j]){
                    newArr.push(arr[i]);
                }
            }
        }
        return newArr
    }
    console.log(newArr);
    /*es6方法*/
    new Set([...document.querySelectorAll("*")].map(v=> v.tagName));
    new Set(Array.form(document.querySelectorAll('*')).map())
</script>
</body>
</html>