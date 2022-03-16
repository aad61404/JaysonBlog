---
sidebar_label: '02_twoSum'
sidebar_position: 4
---
兩個迴圈解太慢，嘗試用其他方法


hashMap
```
var twoSum = function(nums, target) {

    var map = {};
    for(var i = 0 ; i < nums.length ; i++){
        var v = nums[i];

        if(map[target-v] >= 0){
            // 如果 target - v可以在map中找到值x，代表之前已經出現過值x， target = x + v
            // 因此回傳 x的位置與目前v的位置  
            return [map[target-v],i]
        } else {
            // 使用map儲存目前的數字與其位置  

            map[v] = i;
        }
    }
};
```

```
var twoSum = function(nums, target) {
    let matchMap = {};
    for(let i = 0; i < nums.length; i++){
     let compliment = target - nums[i];
        if(compliment in matchMap){
            return [i, matchMap[compliment]]
        }
        matchMap[nums[i]] = i;
    }
};
```