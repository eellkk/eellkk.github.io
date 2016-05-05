# eellkk.github.io
hello there
<!doctype html>
<head>
	<meta charset="utf-8">
	<title>js控制div属性</title>
	<style>
	#inputarea{text-align: center;border-bottom: 1px solid black;padding-bottom: 10px;}
	#thediv{height:300px;width:300px;background: black;margin:30px auto;}
	</style>
	<script>
	function changeStyle(elem,attr,val){
		elem.style[attr] = val;
	}
	window.onload = function(){
		var button = document.getElementsByTagName("input");
			var div = document.getElementById("thediv");
			var attr = ["width","height","background","display","display"];
			var val = ["500px","500px","red","none","block"];
			var oval = ["300px","300px","black","block","block"];
			var inputValue = ["变宽","变高","变色","隐藏"];
		function replay(){	
		for(var j = 0;j < attr.length;j++){
			div.style[attr[j]] = oval[j];
			}
		}
		replay();
		for(var i = 0;i < button.length;i++){
			button[i].index = i;			
			button[i].onclick = function(){
				if(div.style[attr[this.index]] == oval[this.index] ){
					this.index == button.length - 1 && replay();
					changeStyle(div,attr[this.index],val[this.index]);
				}else{
					changeStyle(div,attr[this.index],oval[this.index]);					
				}
			for(var k = 0;k < inputValue.length;k++){
				if(div.style[attr[k]] != oval[k]){
					button[k].setAttribute("value","还原");
				}else{
					button[k].setAttribute("value",inputValue[k]);
				}
			}
			}
		}
	}
	</script>
	</head>
	<body>
		<div id="inputarea">
		<input type="button" value="变宽">
		<input type="button" value="变高">
		<input type="button" value="变色">
		<input type="button" value="隐藏">
		<input type="button" value="重置">
	</div><!-- /.inputarea -->
		<div id="thediv">
		</div>
	</body>
