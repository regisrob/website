---
title: "Lunch locations - Tuesday May 22nd"
layout: washington
tags: [event ]
page:
---

As part of the 2018 IIIF Washington Conference are organising Lunch discussions and on Tuesday we have organised the following:

 * Manuscripts & Archives - lead by Ben Albritton and Anna Naruta-Moya in the Folger Elizabethan Garden
 * Software development - lead by Drew Winget in the Folger lawn facing East Capitol

The idea is that the lunch leaders will gather in a spot and participants will get some lunch from a nearby location and join them for a discussion. It will be a great chance to meet others with similar interests and also start making contacts within the IIIF community. If you would be interested in leading or us organising a lunch discussion on a different topic to the ones listed please get in touch with glen.robson@iiif.io. A map of the locations are below.

Location of nearby lunch locations can be seen at [Folgerpedia page][lunch]
## Lunch Leader locations

<div id="map" style="width: 100%; height: 400px; background-color: grey;" ></div>
<script>
  function initMap() {
    var lc = {lat: 38.8887,lng:-77.0046};
    var map = new google.maps.Map(document.getElementById('map'), {
      zoom: 16,
      center: lc
    });

    // Hide box if there is a click in the map
    map.addListener('click', function() {
                            if (CurrentInfoBox != null) {
                                CurrentInfoBox.close();
                            }
                            CurrentInfoBox = null;
                    });
    markers = [];
    var marker = null;

    function wrapEventCallback(callback){
        var args = Array.prototype.slice.call(arguments, 1);
        return function(e){
            callback.apply(this, args)
        }
    }
    var CurrentInfoBox = null;
    infoBoxFunction = function(index, text) {
        if (CurrentInfoBox != null) {
            CurrentInfoBox.close();
        }
        CurrentInfoBox = new google.maps.InfoWindow({ content: text});
        CurrentInfoBox.open(map, markers[index]);
    };
    var text = "Manuscripts & Archives - lead by Ben Albritton and Anna Naruta-Moya in the Folger Elizabethan Garden"
    var marker = new google.maps.Marker({
      position: {lat: 38.889360069568944, lng:-77.00233273169522},
      title: text,
      map: map
    });
    marker.addListener('click',wrapEventCallback(infoBoxFunction, 0, text));
    markers.push(marker)

    text = "Software development - lead by Drew Winget in the Folger lawn facing East Capitol"
    var marker2 = new google.maps.Marker({
      position: {lat: 38.88957440885658, lng:-77.00289693151296},
      title: text,
      map: map
    });
    marker2.addListener('click',wrapEventCallback(infoBoxFunction, 1, text));
    markers.push(marker2)

    text = "Thomas Jefferson Building, Library of Congress"
    var marker3 = new google.maps.Marker({
      position: {lat: 38.8887,lng:-77.0046},
      title: text,
      map: map
    });
    marker3.addListener('click',wrapEventCallback(infoBoxFunction, 2, text));
    markers.push(marker3)
  }
</script>

<script async defer src="https://maps.googleapis.com/maps/api/js?key=AIzaSyABBvwq6o-hTwwlEaLLK7SLLPC0emBOSjE&callback=initMap" ></script>

[lunch]: https://folgerpedia.folger.edu/Dining_out_near_the_Folger