---
ID: 5188
post_title: mapa-teste
author: Valdecir Carvalho
post_excerpt: ""
layout: page
permalink: http://homelaber.com.br/mapa-teste/
published: true
post_date: 2018-09-14 16:02:30
---
<code>
<html> 
<head> 
  <meta http-equiv="content-type" content="text/html; charset=UTF-8" /> 
  <title>Google Maps Multiple Markers</title> 
  <script src="http://maps.google.com/maps/api/js?key=AIzaSyBYc851tXTheASYSpdury-b68SF95DuOoE"></script>
  <script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-1.10.1.min.js"></script>
</head> 
<body>
  <div id="map" style="width: 900px; height: 400px;"></div>

  <script type="text/javascript">
    

    
    var locations = [
      ['<html> São Paulo, Brasil - Valdecir Carvalho - <a href="https://twitter.com/homelaber" target="_blank">@homelaber</a> - vcarvalho@vmware.com </html>', -23.55052, -46.633309, 3],
      ['Buenos Aires, Argentina', -34.603684, -58.381559, 2],
      ['Assunção, Paraguai', -25.26374, -57.575926, 1]
    ];

    var map = new google.maps.Map(document.getElementById('map'), {
      zoom: 10,
      // center: new google.maps.LatLng(51.530616, -0.123125),
      mapTypeId: google.maps.MapTypeId.ROADMAP
    });

    var infowindow = new google.maps.InfoWindow();

    var marker, i;
    var markers = new Array();

    for (i = 0; i < locations.length; i++) {  
      marker = new google.maps.Marker({
        position: new google.maps.LatLng(locations[i][1], locations[i][2]),
        map: map
      });

      markers.push(marker);

      google.maps.event.addListener(marker, 'click', (function(marker, i) {
        return function() {
          infowindow.setContent(locations[i][0]);
          infowindow.open(map, marker);
        }
      })(marker, i));
    }

    function AutoCenter() {
      //  Create a new viewpoint bound
      var bounds = new google.maps.LatLngBounds();
      //  Go through each...
      $.each(markers, function (index, marker) {
      bounds.extend(marker.position);
      });
      //  Fit these bounds to the map
      map.fitBounds(bounds);
    }
    AutoCenter();

  </script> 
</script></body>
</html>
</code>