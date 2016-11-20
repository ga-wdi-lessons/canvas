# HTML5 Canvas

## Learning Objectives

- Explain what canvas is and why we use it
- Draw pixels using a 2d context

## Framing

- links to things canvas can do
- how would you code that with html and css?
- browser support

## Hello, canvas

```html
<canvas id='canvas'></canvas>
```

```js
var canvas = document.getElementById('canvas')
var ctx = canvas.getContext('2d')
```

`ctx` is short for context. We're telling the browser that the commands
we give will be for a 2d context. Other drawing implementations, like WebGL
use a 3d context.

```js
ctx.fillStyle = 'blue'
ctx.fillRect(0,0,10,10)
             | | |  |
	     | | |  |- height of rect
             | | |- width of rect
             | |- start drawing at y coordinate
             |- start drawing at x coordinate
```

Fill style takes any color:

```
ctx.fillStyle = '#bada55'
ctx.fillStyle = 'green'
ctx.fillStyle = 'rgb(100,200,100)'
ctx.fillStyle = 'rgba(100,200,100,.5)'
```

## You do: Icelandic Flag

>Hint: default canvas size is 300 X 150

![](http://www.crwflags.com/fotw/images/i/is-u1897.gif)

Bonus! Try the flag of scotland

## More Shapes With Canvas

The only other primitive shape in Canvas is the `path`. A path is a list of points,
connected by lines that can be curved or straight.

To create a path:

1. `beginPath`
2. Use drawing commands
  - `moveTo`
  - `lineTo`
3. Close the path
4. Optionally stroke or fill the path

```js
ctx.beginPath()
ctx.moveTo(50,50) // x and y
ctx.lineTo(50,100)
ctx.lineTo(100,100)
ctx.fill()
```

### Drawing Circles

```js
ctx.moveTo(10,20) // x and y to start drawing
ctx.arc(20,20,10,0,Math.PI*2)
        |  |  |  | |- The end angle. 2*pi == 360 (1.5 is 3/4)
        |  |  |  |- The start angle. 0 == start (1 is 1/2)
	|  |  |- radius of the circle
	|  |- start drawing at y
	|- start drawing at x
ctx.closePath()
ctx.stroke()
```

A stroke is like a border

## You do: Draw a Smiley face!

## Break

## Mini-lab: Snake

- solution: https://ga-wdi-exercises.github.io/canvas-snake/
- starter code: https://github.com/ga-wdi-exercises/canvas-snake