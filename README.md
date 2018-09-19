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
<button onclick="getLocation()">Try It</button>

<p id="demo"></p>

<script>
var x = document.getElementById("demo");

function getLocation() {
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition);
    } else { 
        x.innerHTML = "Geolocation is not supported by this browser.";
    }
}

function showPosition(position) {
    x.innerHTML = "Latitude: " + position.coords.latitude + 
    "<br>Longitude: " + position.coords.longitude;
}
</script>
<p id="demo"></p>

<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Your SOS message was sent!";
}
</script>

</script>
  
</body>

               
