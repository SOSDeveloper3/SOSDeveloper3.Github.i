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
if (navigator.geolocation) {
  console.log('Geolocation is supported!');
}
else {
  console.log('Geolocation is not supported for this Browser/OS version yet.');
}
  <div id="tripmeter">
  <p>
    Starting Location (lat, lon):<br/>
    <span id="startLat">???</span>°, <span id="startLon">???</span>°
  </p>
  <p>
    Current Location (lat, lon):<br/>
    <span id="currentLat">???</span>°, <span id="currentLon">???</span>°
  </p>
  <p>
    Distance from starting location:<br/>
    <span id="distance">0</span> km
  </p>
</div>
  window.onload = function() {
  var startPos;
  navigator.geolocation.getCurrentPosition(function(position) {
    startPos = position;
    document.getElementById('startLat').innerHTML = startPos.coords.latitude;
    document.getElementById('startLon').innerHTML = startPos.coords.longitude;
  });
};
  window.onload = function() {
  var startPos;
  navigator.geolocation.getCurrentPosition(function(position) {
    // same as above
  }, function(error) {
    alert('Error occurred. Error code: ' + error.code);
    // error.code can be:
    //   0: unknown error
    //   1: permission denied
    //   2: position unavailable (error response from locaton provider)
    //   3: timed out
  });
};
  navigator.geolocation.watchPosition(function(position) {
  document.getElementById('currentLat').innerHTML = position.coords.latitude;
  document.getElementById('currentLon').innerHTML = position.coords.longitude;
});
  navigator.geolocation.watchPosition(function(position) {
  // same as above
  document.getElementById('distance').innerHTML =
      calculateDistance(startPos.coords.latitude, startPos.coords.longitude,
                        position.coords.latitude, position.coords.longitude);
});
  function calculateDistance(lat1, lon1, lat2, lon2) {
  var R = 6371; // km
  var dLat = (lat2 - lat1).toRad();
  var dLon = (lon2 - lon1).toRad(); 
  var a = Math.sin(dLat / 2) * Math.sin(dLat / 2) +
          Math.cos(lat1.toRad()) * Math.cos(lat2.toRad()) * 
          Math.sin(dLon / 2) * Math.sin(dLon / 2); 
  var c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a)); 
  var d = R * c;
  return d;
}
Number.prototype.toRad = function() {
  return this * Math.PI / 180;
}
 
<p id="demo"></p>
  <p id="demo"></p>
</body>

