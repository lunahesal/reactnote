最终显示结果要用到图表，虽然 https://github.com/vuejs/awesome-vue#charts 上有很多图表可以选择。但是由于我们这里的 chart 都非常的简单，所以可以用 svg 直接自己手动制作。

参考：https://codepen.io/jonitrythall/pen/zGWXeO


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="main.css">
  <style>
    svg {
      width: 130px;
      height: 130px;
    }
  </style>
</head>
<body>
<h1>68%</h1>
<svg width="100" height="100" viewBox="0 0 32 32">
  <circle id="percent"
    r="16" cx="16" cy="16" fill="#fff" stroke="green" stroke-width="12" />
  <circle id="background"
    r="16" cx="16" cy="16" fill="#fff" fill-opacity="0.5" stroke="pink" stroke-width="12" stroke-dasharray="68 100" />
</svg>
</body>
</html>
```


### 统计每个投票项的得票数

```js
下面的 options 和 votes 的数据都可以从 store 中直接得到
let options = [
  {
    id: 1,
    name: '鱼香肉丝'
  },
  {
    id: 2,
    name: '宫保鸡丁'
  }
]

let votes = [
  {
    id: 1,
    optionId: 2
  },
  {
    id: 2,
    optionId: 1
  },
  {
    id: 3,
    optionId: 1
  },
  {
    id: 4,
    optionId: 1
  }
]

let result = options.map(
  t => {
    const voteCount = votes.filter(
      item => item.optionId === t.id
    ).length
    return {
      OptionId: t.id,
      voteCount
    }
  }
)

console.log('+++result+++', result)
```

### 根据投票结果排名

上这不可以得到类似如下的数据

```js
[ { OptionId: 1, voteCount: 1 }, { OptionId: 2, voteCount: 3 } ]
```

根据上面的结果，按照得票数由多到少排序：

```
const result = [
  { OptionId: 1, voteCount: 7 },
  { OptionId: 2, voteCount: 3 },
  { OptionId: 3, voteCount: 3 },
  { OptionId: 4, voteCount: 1 },
]

// sort by voteCount
const sortedResult = result.sort(function (a, b) {
  return a.voteCount - b.voteCount;
});

console.log(sortedResult)
```



打印结果

```
[ { OptionId: 4, voteCount: 1 },
  { OptionId: 2, voteCount: 3 },
  { OptionId: 3, voteCount: 3 },
  { OptionId: 1, voteCount: 7 } ]
```




### 展示排序后的数据

https://github.com/happypeter/voteup/commit/f4230069fdef4cd8d4287de4f083e3fc4a6e1b87
