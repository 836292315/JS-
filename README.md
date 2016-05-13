<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>表单</title>
	<script type="text/javascript" src="EventUtil.js"></script>
  </head>
<body>

	<!--通用提交按钮-->
	<input type="submit" value="Submit Form">
	<!--自定义提交按钮-->
	<button type="submit">Submit Form</button>
	<!--自定义提交按钮-->
	<button type="submit">Submit Form</button></br>
	<!--图像按钮-->
	<input type="image" src="zhang/1.jpg"></br>
	
	<!--通用重置按钮-->
	<input type="reset" value="Reset Form">
	<!--自定义重置按钮-->
	<button type="reset">Reset Form</button>
	
	<form method="post"  action="javascript:alert('Form submitted!')" id="myForm">
		<ul>
			<li><input type="radio" name="color" value="red">Red</li>
			<li><input type="radio" name="color" value="blue">Blue</li>
			<li><input type="radio" name="color" value="green">Green</li>
		</ul>
		<input type="submit" value="Submit Form" name="submit-btn">
        <button type="button">Whatever</button>
	</form>
<script type="text/javascript">


/*
	var form = document.getElementById("myForm");
	
	
	var colorFields = form.elements["color"];
	alert(colorFields.length);
	
	var firstColorField = colorFields[0];
	var firstFormField = form.elements[0];
	alert(firstColorField === firstFormField);    //true
*/

/*
(function(){
    var form = document.getElementById("myForm");
            
    var colorFields = form.elements["color"];
    alert(colorFields.length);  //3
            
    var firstColorField = colorFields[0];
    var firstFormField = form.elements[0];
    alert(firstColorField === firstFormField);   //true

})();
*/
		(function(){
            var form = document.forms[0];
            
            //Code to prevent multiple form submissions
            EventUtil.addHandler(form, "submit", function(event){
                event = EventUtil.getEvent(event);
                var target = EventUtil.getTarget(event);
            
                //get the submit button
                var btn = target.elements["submit-btn"];
            
                //disable it
                btn.disabled = true;
                
            });

        })();

</script>
</body>
</html>
