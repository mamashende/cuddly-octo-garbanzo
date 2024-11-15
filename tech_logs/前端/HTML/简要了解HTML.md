简要了解HTML
超文本语言，可以包含丰富内容的标记语言

标记（标签）语言
```
<h1>这是标签语言<hi>
<img src="photo.jpg" /> //空标签
```

<!doctype html>
决定html渲染格式的规则文件

```html
<!DOCTYPE html>

<html>

<body>

<h1>字体排印学</h1>

<h2>历史</h2>

<p>活字的雏形或可追溯至公元前两千年前后美

索不达米亚文明的乌鲁克和拉尔萨，砖块上面不

均匀的印花被视作有可能是活字思想雏形。</p>

<h3>印刷体源流</h3>

<p>中国在唐代就已经出现雕版印刷术，公元868

年的《金刚经》是现存最古老的印刷品之一，使用

的技术即是木雕版印刷。</p>

<h2>应用</h2>

<p>...</p>

</body>

</html>
```

浏览器将html解析为DOM树

常用各种标签
```html
//排版字号标签h1到h6
<h1>阿巴阿巴</h1>

//列表标签
<li></li>
有三种细分

//顺序列表，自动附带一个序列号
<ol>
	<li></li>
</ol>

//无顺序列表
<ul>
	<li></li>
</ul>

//键值对式，可以多对多关系
<dl>
	<dt></dt>
	<dd></dd>
</dl>


//链接
<a>

<a href="https://github.com/">

//图片
<img 
	 src=""
	 alt=""
	 width=""
/>

//音频，视频
<audio
	src=""
	controls
></audio>

<video
	src=""
	controls
></video>


//控件

//输入窗口
<input placeholder="请输入">

<input type="range">


<input type="number" min="1" max="100" >


<input type="date" min="2024-11-2">

//多行输入文本框
<textarea>Hi</textarea>

//选项框
<input type="checkbox" />

//多项单选框
<p>

<label><input type="radio" name="sport" />⚽</label>

<label><input type="radio" name="sport" />🏀</label>

</p>


//下拉式多项选择框
<p>

<select>

<option>🥑</option>

<option>🥩</option>

<option>🥓</option>

</select>

</p>


//带提示词的输入/选择框
<input list="countries" />

<datalist id="countries">

<option>Greece</option>

<option>United Kingdom</option>

<option>United States</option>

</datalist>



//js脚本标签
<script src=""/>
```


文本相关的标签
```html
 
```

通过语义化的方式去规范地写html