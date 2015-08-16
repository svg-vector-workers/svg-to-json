#SVG to JSON
A method to convert a string of SVG to JSON data, and optionally render statistics.

#Usage
Create a new instance, provide `svg` string and optionally pass in `options`.

```js
var svg_json = new SVGToJSON(svg[, options]);
```

#API
##Object.json
`SVGToJSON()` returns an object. `OBJ.json` is the primary JSON data. It is an array of all SVG tags.

```js
var svg_json = new SVGToJSON(svg);

svg_json = {
  json: [...] 
}
```

##Object.json[i]
Each tag in `Object.json` has four values.

```js
var first_tag = svg_json.json[0];

first_tag = {
  attrs: {
    "height": "600",
    "viewBox": "0 0 800 600",
    "width": "800",
    "xmlns": "http://www.w3.org/2000/svg",
    "xmlns:xlink": "http://www.w3.org/1999/xlink"
  },
  name: "svg",
  pos: 0,
  type: "open"
}
```

###`attrs` (object)
Key-value pairs for each attribute on the tag.

###`name` (string)
The tag name.

###`pos` (integer)
The tab position of the tag.

###`type` (string)
The type of tag. `open`, `close`, or `closeself`.


##Object.stats (Object)
If stats are requested, `SVGToJSON` additionally returns `OBJ.stats` object. `OBJ.stats` contains counts for `attributes` and `elements`.

```js
"stats": {
  "attributes": {
    "height": 1,
    "viewBox": 1,
    "width": 1,
    "xmlns": 1,
    "xmlns:xlink": 1
  },
  "elements": {
    "svg": 1
  }
}
```