## 地牢生成


在做FCC习题的时候,有一题React的题目需要制作一个简单的游戏,需要创建一个随机的地下城,当时没有什么好的想法,就用了一个空壳方块,最近有时间,自己想了一个;

起初,在网上搜到了一个 逐个生成房间的算法,理解了一下 很不错,但是我个人比较喜欢混乱的,类似于“贪婪洞穴”的那种地图,所以我就自己制作了这样一个生成地牢的方法;

刚学习前端没多久,但是想法确实是我自己想出来的,如有雷同肯定是巧合哈哈! 菜鸟上路,大牛们多多照顾;


## 思考

生成一个地牢,首先我认为比较关键的几点是:

  - 所有的点必须都联通,不能出现无法到达的点;
  - 地图每次都具有随机性,而不是简单的变化;
  - 可走的路要多,不可只是唯一的路;

起初,我想到的是,能否通过 生成不同的方块,然后填充到大方块中,但是我觉得这样做,地图上始终就是一块块方的,顶多也是一个个三角,一个个圆之类的... 因此我放弃了这种方式;

### 整个算法其实就3步

  1. 从地图上随机选择2个点,一个做为`起点A`，另外一个`终点B`;

  2. 创建从`起点A` 到 `终点B` 的曲折路径;

  3. 循环创建路径,直至满意;

### 可进行优化的点

  1. 需要保持地图所有的点都能走到

   解决方案：除了第一条线路,之后的线路`必须经过`已经创建的路径;这样就能保证所有的路都是`通`的;
   
  2. 地图不龟缩在一个角落,或者使用非常多的时间去尝试;

   解决方案; 让第一条线路的2个点`相距足够远`;这样能保证后面的生成的路径`成功率`大大`增加`;
   
### Demon

  


  