---

layout: postMod1
title: Interactive Directed Graphs for Angular
author: pulkit
last_modified_at: February 09, 2018
tags: [angular,directed,graph,editor,interactive]

---

## Motivation

Find the most mature and visually appealing libraries that offer drop-in components for creating <u>interactive directed graphs</u> within an Angular application.

## Accessment Matrix
| | Interactive | Renders Quickly | Visually Appealing | Goals Align | Free |
|-|-|-|-|-|-|
| lsharir/angular-d3-graph-example | 
| MX Graph | Yes | Average | Yes | No | Maybe |
| NGX Graph | Unsure | Average | Yes | Maybe | Maybe |
| Rete | Yes | Average | Yes | No | Maybe |
| sigmajs | ? | ? | ? | ? | ? |
| visJS | ? | ? | ? | ? | ? |

## Notes

* An article for hands-on [practice](https://medium.com/netscape/visualizing-data-with-angular-and-d3-209dde784aeb)
  * With a [repo](https://github.com/lsharir/angular-d3-graph-example) that can be [launched on StackBlitz directly](https://stackblitz.com/github/lsharir/angular-d3-graph-example) successfully!
* Very impressive [live example](http://bl.ocks.org/rkirsling/5001347)
  * [Another example](http://rkirsling.github.io/modallogic/) by author of said example
    * Someone wrote an [article](https://medium.com/@balramchavan/building-d3-force-graph-editor-angular-7-a9d5cd3cbc97) stating that they wrapped the previous author's logic for reuse within angular.
      * [repo](https://github.com/ultrasonicsoft/ng-d3-graph-editor)
      * [live example](http://d3-graph-editor.surge.sh/)
* [NGX Graph](https://github.com/swimlane/ngx-graph)
	* [Live Preview](https://swimlane.github.io/ngx-graph)
	* An example can be [launched on StackBlitz](https://stackblitz.com/edit/ngx-graph-simple-example)
	* Does not seem to be "interactive"
* [Rete](https://github.com/retejs/rete)
  * [Live Preview](https://codesandbox.io/embed/9jp88p1jpy?view=preview)
  * Seems to be geared towards a different goal than what we set out to achieve.
* Commercial / Paid
	* goJS
	  * https://gojs.net/latest/samples/conceptMap.html
	  * https://gojs.net/latest/samples/mindMap.html
	* [jsPlumbToolkit](https://jsplumbtoolkit.com/community/demo/animation/index.html)
	* [JointJS](http://resources.jointjs.com/demos/shortest-path)
* https://cytoscape.org/cytoscape.js-edgehandles/
* http://sigmajs.org/
	* Couldn't find any interactive examples so cannot call it a qualified lead without digging some more.
* MX Graph
	* https://jgraph.github.io/mxgraph/javascript/index.html
    * https://jgraph.github.io/mxgraph/javascript/examples/tree.html
* visJS
  * http://visjs.org/network_examples.html
  * http://visjs.org/examples/network/events/interactionEvents.html


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ3MzIxNzE2NCwtMTIyNjc4MDUwMl19
-->