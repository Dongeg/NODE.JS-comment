# NODE.JS-comment
node.js评论灌水方法
```
var http=require('http');

var querystring=require('querystring');
//正常发送一条评论从浏览器开发者工具中可以看到需要的信息
var postData=querystring.stringify({

	'content':'thank you very much,i am test success!',
	'mid':8837
});
//从请求头中复制，并修改格式为对象形式
var options={
	hostname:'www.imooc.com',
	port:80,
	path:'/course/docomment',
	method:'POST',
	headers:{
		'Accept':'application/json, text/javascript, */*; q=0.01',
		'Accept-Encoding':'gzip, deflate',
		'Accept-Language':'zh-CN,zh;q=0.8',
		'Connection':'keep-alive',
		'Content-Length': postData.length,
		'Content-Type':'application/x-www-form-urlencoded; charset=UTF-8',
		'Cookie':'imooc_uuid=dfa597da-ab5f-490a-8428-466d39019314; imooc_isnew_ct=1461119616; bdshare_firstime=1469346035841; loginstate=1; apsid=M1OTZhNDk2NjhjZDg3MzNiMTAzZWQyMmFkZWZmZTEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAMzQ2OTAzMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAxOTExMjAzNTQxQHFxLmNvbQAAAAAAAAAAAAAAAAAAAGMyYTY3OGJmMWNjYjQ3M2MyODUxODY3N2NkYzU4NTE1YbzYV2G82Fc%3DMW; last_login_username=1911203541%40qq.com; PHPSESSID=ii3atqm4qfck2d5csbr17iilq1; jwplayer.qualityLabel=è¶æ¸; IMCDNS=0; Hm_lvt_f0cfcccd7b1393990c78efdeebff3968=1473821783,1473899583,1473910924,1473989860; Hm_lpvt_f0cfcccd7b1393990c78efdeebff3968=1474018311; imooc_isnew=2; cvde=57db4cdfe84f1-38',
		'Host':'www.imooc.com',
		'Origin':'http://www.imooc.com',
		'Referer':'http://www.imooc.com/video/8837',
		'User-Agent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko)Chrome/52.0.2743.82 Safari/537.36',
		'X-Requested-With':'XMLHttpRequest'		
	}
}

var req=http.request(options,function(res){
	console.log('Status:'+res.statusCode)

	res.on('end',function(){
		console.log('success')
	})
})
req.on('error',function(e){
	console.log('error: '+e.message)
})
req.write(postData)
req.end()
```
