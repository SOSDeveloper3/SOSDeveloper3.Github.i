# SOS
  <body>
  <h6>What is going on?</h6>
<form >
<input type="radio" name="choice" value="Robbed"> Robbed
<input type="radio" name="choice" value="Kidnapped"> Kidnapped
<input type="radio" name="choice" value="Medical Emergency"> Medical Emergency
  <input type="radio" name="choice" value="Physical Assualt"> Physical Assualt
</form>
<button onclick="getLocation()">Submit</button>
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
  <p id="demo"></p>
  <iframe src="doesnt-matter" class="hidden" name="sneaky"></iframe>

<form method="post" action="." target="sneaky">
    <input type="hidden" name="confirm" value="1" />
    <input type="submit" value="OK" />
</form>
.hidden {
    display:none;
}
</body>

