# What's nodegrass-lite

======
 Fork nodegrass forked from scottkiss/nodegrass
 
 up iconv-lite 0.4.5
 
 I want to support Big5,

 nodegrass-lite is a tool to process client request for Node.js
  
## Install
```bash
$ npm install nodegrass-lite
```

  
## Useage
```js


var iconv = require('iconv-lite'); 
iconv.extendNodeEncodings(); 

//以测试通过：
//http://125.88.27.3:18091/api?encoding=big5&url=http://www.hkex.com.hk/chi/csm/script/tc_QuotaUsage.js?Token=70556 
//http://125.88.27.3:18091/api?encoding=utf8&url=http://www.hkex.com.hk/chi/csm/script/tc_QuotaUsage.js?Token=70556

//get request
var nodegrass = require('nodegrass-lite');
nodegrass.get("https://github.com",function(data,status,headers){
	console.log(status);
	console.log(headers);
	console.log(data);
},null,'utf8').on('error', function(e) {  // or  },null,'big5').on('error', function(e) {
    console.log("Got error: " + e.message);
});

//download file
var nodegrass = require('nodegrass-lite');
nodegrass.getFile('http://www.xxx.com/XXXX.jpg','d:/cccc/yep.jpg',function(e){
	if(e){
		console.log(e);
	}
	console.log('download success!');
});

```
## License

(The MIT License)

Copyright (c) 2011-2015 sk &lt;jenner.luo@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
  
