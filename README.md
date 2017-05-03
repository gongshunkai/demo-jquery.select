<h2># demo-jquery.select v1.0</h2>
<p>jquery插件 ( 多级联动下拉菜单 ) - jquery.select v1.0</p>
<p>支持本地数据或ajax数据</p>
<p><b>演示地址：</b><a href="http://gongshunkai.github.io/demo/%E5%A4%9A%E7%BA%A7%E8%81%94%E5%8A%A8%E4%B8%8B%E6%8B%89%E8%8F%9C%E5%8D%95/demo.html">http://gongshunkai.github.io/demo/%E5%A4%9A%E7%BA%A7%E8%81%94%E5%8A%A8%E4%B8%8B%E6%8B%89%E8%8F%9C%E5%8D%95/demo.html</a></p>
<p><b>使用方法：</b></p>
<p>var sel = $('.area').select({<br>&nbsp;&nbsp;
dataMenu:unit,<br>&nbsp;&nbsp;
selects:$('.area select'),<br>&nbsp;&nbsp;
visible:2,<br>&nbsp;&nbsp;
showEmpty:true,<br>&nbsp;&nbsp;
async:true,<br>&nbsp;&nbsp;
url:function(id){<br>&nbsp;&nbsp;
&nbsp; &nbsp; return 'data/data' + id + '.json';<br>&nbsp;&nbsp;
},<br>&nbsp;&nbsp;
beforeLoad:function(elem,value,opts){<br>&nbsp;&nbsp;
&nbsp; &nbsp; elem.attr('empty-text','正在加载中...');<br>&nbsp;&nbsp;
&nbsp; &nbsp; sel.select.setSelect(elem,[],opts);<br>&nbsp;&nbsp;
&nbsp; &nbsp; elem.show();<br>&nbsp;&nbsp;
},<br>&nbsp;&nbsp;
afterLoad:function(elem,value,opts,data){<br>&nbsp;&nbsp;
&nbsp; &nbsp; elem.attr('empty-text',elem.attr('original-text'));<br>&nbsp;&nbsp;
&nbsp; &nbsp; sel.select.setSelect(elem,data,opts);<br>&nbsp;&nbsp;
},<br>&nbsp;&nbsp;
onError:function(elem,value,opts,data){<br>&nbsp;&nbsp;
&nbsp; &nbsp; elem.attr('empty-text','数据加载失败了');<br>&nbsp;&nbsp;
&nbsp; &nbsp; sel.select.setSelect(elem,[],opts);<br>&nbsp;&nbsp;
&nbsp; &nbsp; elem.show();<br>
&nbsp;&nbsp;
}<br>
});</p>
<p>初始化提供1个配置项参数</p>
<p>{<br>
  &nbsp;&nbsp;&nbsp;&nbsp;
  dataMenu:null, //数据<br>&nbsp;&nbsp;&nbsp;&nbsp;
  selects:null, //select集合<br>&nbsp;&nbsp;&nbsp;&nbsp;
  visible:0, //空值显示的数量<br>&nbsp;&nbsp;&nbsp;&nbsp;
  showEmpty:false, //是否显示空值(位于第一个)<br>&nbsp;&nbsp;&nbsp;&nbsp;
  async:false, //是否启用ajax(为true时下面参数有用)<br>&nbsp;&nbsp;&nbsp;&nbsp;
  url:null, //请求地址<br>&nbsp;&nbsp;&nbsp;&nbsp;
  postData:null, //发送数据<br>&nbsp;&nbsp;&nbsp;&nbsp;
  beforeLoad:null, //请求前的回调<br>&nbsp;&nbsp;&nbsp;&nbsp;
  afterLoad:null, //请求后的回调<br>&nbsp;&nbsp;&nbsp;&nbsp;
  onError:null, //错误的回调<br>
  };</p>