
<script src="https://cdnjs.cloudflare.com/ajax/libs/openseadragon/3.0.0/openseadragon.min.js" integrity="sha512-Dq5iZeGNxm7Ql/Ix10sugr98niMRyuObKlIzKN1SzUysEXBxti479CTsCiTV00gFlDeDO3zhBsyCOO+v6QVwJw==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

## OpenSeadragon

This is a demo of the [OpenSeadragon](https://openseadragon.github.io/) viewer. This viewer works with IIIF Image API images and is included in many of the more advanced viewers like Mirador and the UV.

Use your mouse wheel to zoom in or use the + or - minus buttons


<div id="osd" style="width: 100%; height: 586px"></div>

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

    var infoJson = getURLParameter("iiif-content");
    OpenSeadragon({
            id:                 "osd",
            prefixUrl:          "https://cdnjs.cloudflare.com/ajax/libs/openseadragon/3.0.0/images/",
            preserveViewport:   true,
            visibilityRatio:    1,
            minZoomLevel:       1,
            defaultZoomLevel:   1,
            sequenceMode:       true,
            tileSources:   [infoJson]
        });
</script>
