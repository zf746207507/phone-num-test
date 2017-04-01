# phone-num-test
test your phone-num input

<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript" src="jquery-1.11.0.js" ></script>
	</head>
	<body>
		<div>
			<p>
				<span>手机号：</span>
				<input type="tel" class="tel" id="mobile" required placeholder="请输入您的手机号">
			</p>
			<p>
				<span>验证码：</span>
				<input type="tel" id="code-input" placeholder="请输入验证码" />
				<span id="code-get">获取验证码</span>
			</p>
			<button id="button">确认</button>
			<p style="display: none;" class="none">验证码错误</p>
		</div>
	</body>
</html>
<script>
	(function() {
	    $('#mobile').blur(function(){
	    	var re =/^1\d{10}$/;
	    	var val=$("#mobile").val();
    		if (re.test(val)) {
                $('#code-get').click(function() {
                	var second=60;
                	var int=setInterval (time,1000);
                	function time() {
                		second--;
                		$('#code-get').html(second);
                		if(second<=0) {
                			$('#code-get').html('请重新获取验证码');
                            clearInterval(int);
                			second=60;
                		}
                	}
                	
                })
            } else {
                alert('请输入您的手机号');
            }
  		});
  		$('#button').click(function() {
  			var Xcode=$('#code-input').val();
  			var a=123;
  			if(Xcode!=a) {
  				$('.none').css('display','block');
  				function dispear() {
  					$('.none').css('display','none');
  				}
  				setTimeout(dispear,2000);
  			}
  			
  		})
	})();
</script>
