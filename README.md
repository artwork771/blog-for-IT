学习php程序的备份

使用前端技术，javascirpt或者jquery可以跨框架访问元素， 本人所做的案例为，框架外访问框架内的元素。
      
      var otn   = document.getElementById('as'); 该iframe框架id是as
		  window.onload=function(){
		  console.log(otn.contentDocument);} 

使用js 得到框内的文档对象 document 必须全页面加载完毕后才可以确定文档，否则文档Body是空的。

    window.onload=function(){   
	$("#testIframe").contents().find('form').
	  submit(function(){
		setTimeout(function(){
          alert("SAS");},2000);
       });
     };
使用jquery得到文档对象，框架内有一张表单，提交表单约2秒中后，主页面弹出提示。同时副页面3秒跳转。

一开始尝试用on绑定动态元素，但是仍然框架里面的对象是空的，后来发现需要页面彻底加载完毕后动态元素就可以使用了。
window.onload  
jquery的ready函数在案例中已经被用过一次不能再用。
