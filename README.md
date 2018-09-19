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
<head runat="server">
    <title>Geolocation</title>
    <script src="../../Scripts/jquery-1.4.1.js" type="text/javascript"></script>
    <script src=http://maps.googleapis.com/maps/api/js?sensor=false 
type="text/javascript"></script> 
 
    <script type="text/javascript">
        $(document).ready(function () {
            var message = $("#message");
            var position = $("#position");
            if (window.navigator.geolocation) {
                message.html("locating");
                var geolocation = window.navigator.geolocation;
                var options = { enableHighAccuracy: true}
                geolocation.getCurrentPosition(onComplete, onFail, options);             }
            else {
                message.html("No support");
            }
        });
 
        function onComplete(geoPosition) {
            $("#position").append("<p> Latitude" + geoPosition.coords.latitude + "</p>");
            $("#position").append("<p> Longitude" + geoPosition.coords.longitude + "</p>");
            Initializemap(geoPosition.coords.latitude, geoPosition.coords.longitude);
        }
 
        function onFail() {
            alert("Failed ");
        }
 
        function Initializemap(latitude, longitude) {
 
            var Latlng = new google.maps.LatLng(latitude, longitude);
            var options = {zoom: 18, center: Latlng, mapTypeId: google.maps.MapTypeId.ROADMAP };
            var map = new google.maps.Map(document.getElementById("map"),options);
        }
    </script>
</head>
  
</body>

               
