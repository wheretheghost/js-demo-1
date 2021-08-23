##  声明对象的两种语法


1.
```
let obj = {'name':'frank','age':18}
```
2.
```
let obj = new Object({'name':'frank'})
```

##  如何删除对象的属性

1.
`delete obj.xxx`


`delete obj[`xxx`]`

2.
`'xxx' in obj ===false`

3.
`'xxx' in obj && obj.xxx === undefined`

  
##  如何查看对象的属性

1.
`Object.values(obj)`
`Object.keys(obj)`

2.
`console.dir(obj)`

3.
`obj.hasOwnProperty('toString')`

4.
`Object.entires.(obj)`

5.
`obj.__proto__


##  如何修改或增加对象的属性

1.
`let obj = {name:'frank'}`

2.
`obj.name = 'frank'`

3.
`obj['name'] = 'frank'`

4.
`obj['na'+'me'] = 'frank'`

5.
`let key = 'name';obj[key] = 'frank'`

##   'name' in obj和obj.hasOwnProperty('name') 的区别

 'name' in obj主要用以判断目标属性是否包含在对象中，但无法区别该属性为自己的还是共有的，obj.hasOwnProperty('name')主要用以判断该属性为自身还是共有的 
