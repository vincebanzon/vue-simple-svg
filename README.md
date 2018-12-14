# vue-span-svg
Base from vue-simple-svg but instead of using div, this uses span.
A simple Vue.js plugin that allows you to use a component that loads a .svg image as an inline SVG so you can easily control its fill color from the parent component. No jQuery required.

### Installation:
```sh
$ npm install vue-span-svg
```

### Usage:
initialize in your Vue's main file,
```javascript
// as a plugin
import VueSpanSVG from 'vue-span-svg'
Vue.use(VueSpanSVG)

// or as a component
import {SpanSVG} from 'vue-span-svg'
Vue.component('span-svg', SpanSVG)
```

and use in your component,
```html
<span-svg
  :filepath="'/PATH_/TO_/YOUR_/FILE.svg'"
  :fill="getFillColor"
  :stroke="getStrokeColor"
  :width="'400px'"
  :height="'400px'"
  :id="'custom-id'"
  @ready="onSvgReady()"
  />
```

### Available props and events:
| props | type | description | default |
| ------ | ------ | ------ | ------ |
| filepath | string | path to your svg file | |
| fill | string | svg's fill color | 'black' |
| stroke | string | svg's stroke color | 'black' |
| width | string | svg's width | '1em' |
| height | string | svg's height | '1em' |
| id | string | custom color | '' |
| preserve | boolean | preserve original color | false |

| events | description |
| ------ | ------ |
| @ready | called when the svg is loaded |


### Notes:
- inline svg element has a class '.span-svg'
- inline svg has a div wrapper with a class '.span-svg-wrapper'
- fill/stroke style set to a path of a SVG will be removed unless its value is 'none' or preserveColor is true

### Demo:
![result](https://media.giphy.com/media/26FeVejNWHXsZiaIM/giphy.gif)

To run demo in your local environment,
```sh
$ npm run dev-demo
```
You can find the code of an example component that has a simple-svg component as its child in demo/components/SvgButton.vue


### Todo:
- enable applying various colors to multiple paths in an SVG


### Reference:
- Loading a SVG with XMLHttpRequest and DOMParser https://github.com/jonnyhaynes/inline-svg
- Parsing inline svg tags https://github.com/MMF-FE/vue-svgicon
