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
utton.onclick = function() {
  var startPos;
  var nudge = document.getElementById("nudge");

  var showNudgeBanner = function() {
    nudge.style.display = "block";
  };

  var hideNudgeBanner = function() {
    nudge.style.display = "none";
  };

  var nudgeTimeoutId = setTimeout(showNudgeBanner, 5000);

  var geoSuccess = function(position) {
    hideNudgeBanner();
    // We have the location, don't display banner
    clearTimeout(nudgeTimeoutId);

    // Do magic with location
    startPos = position;
    document.getElementById('startLat').innerHTML = startPos.coords.latitude;
    document.getElementById('startLon').innerHTML = startPos.coords.longitude;
  };
  var geoError = function(error) {
    switch(error.code) {
      case error.TIMEOUT:
        // The user didn't accept the callout
        showNudgeBanner();
        break;
    }
  };

  navigator.geolocation.getCurrentPosition(geoSuccess, geoError);
};
  
</body>

               
