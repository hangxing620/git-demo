# 正则 -- 入门级

## 字符组

### 横向匹配

```javascript
var regular = /ab{2,3}c/g
var string = "abc abbc abbbc abbbbc"

console.log(string.match(regular)) // ["abbc abbbc"]
```