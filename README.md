# SOS
  <body>
  <h6>What is going on?</h6>

<form >
<input type="radio" name="choice" value="Robbed"> Robbed
<input type="radio" name="choice" value="Harrased"> Harrased
<input type="radio" name="choice" value="Kidnapped"> Kidnapped
<input type="radio" name="choice" value="Injured"> Injured
</form>
<button onclick="myFunction()">Submit</button>

<p id="demo"></p>

<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Your SOS message was sent!";
}
</script>

  
</body>

               
