
<script src="https://ncsu-libraries.github.io/annona/dist/annona.js"></script>
<link rel="stylesheet" type="text/css" href="https://ncsu-libraries.github.io/annona/dist/annona.css">

## Annona Storyboard viewer

This is a demo of the [Annona Storyboard viewer](https://ncsu-libraries.github.io/annona/) by Niqui O'Neill from NC State University Libraries. Annona allows you to navigate through your annotations and can be a useful way of sharing them with others.

Use the left and right arrow keys below to navigate through your annotations.

<div id="storyboard"></div>
        

<script type="text/javascript">
    // From Getty code: http://www.getty.edu/art/collection/static/viewers/mirador/?manifest=https://data.getty.edu/museum/api/iiif/1895/manifest.json
    function getURLParameter(param) {
        if(typeof(param) == "string" && param.length > 0) {
            if(typeof(window.location.search) == "string" && window.location.search.length > 0) {
                var _results = new RegExp(param + "=([^&]*)", "i").exec(window.location.search);
                if(typeof(_results) == "object" && _results !== null && typeof(_results.length) == "number" && _results.length > 0 && _results[1]) {
                    if(typeof(_results[1]) == "string" && _results[1].length > 0) {
                        return unescape(_results[1]);
                    }
                }
            }
        }
        return null;
    }

    var annotationList = getURLParameter("iiif-content");
    if(typeof(annotationList) == "string" && annotationList.length > 0) {
        var div = document.getElementById("storyboard");
        div.innerHTML = "<iiif-storyboard annotationlist='" + annotationList + "'></iiif-storyboard>"
    }
</script>
