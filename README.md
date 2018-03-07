# myr.js

**myr.js** is a WebGL 2 based 2D graphics renderer. The engine is optimized for rendering large amounts of sprites, and also supports render targets, custom shaders, primitives and advanced transformations. There are no external dependencies. **myr.js** has been licensed under the [MIT license](LICENSE). All source code is contained in the [myr.js](js/myr.js) file.

# Documentation

## Initialization
**myr.js** can be initialized by calling the `Myr` function, which requires a canvas element as an argument. All global functions and objects are members of the returned object. The provided canvas must be able to provide a *WebGL 2* context.

Initialization would typically look like this:
```javascript
// Create a myr.js object
let myr = new Myr(document.getElementById("some-canvas-id"));

// Access myr.js functions and classes from here on
myr.setClearColor(new myr.Color(0.2, 0.5, 0.7));
```

## Objects
The **myr.js** object exposes several objects:

Object | Description
-|-
[`Surface`](#surface)|A render target which can be rendered to, which may be initialized to an existing image
[`Shader`](#shader)|A (custom) shader
[`Transform`](#transform)|A 2D transformation
[`Color`](#color)|A color containing a red, green, blue and alpha channel
[`Vector`](#vector)|A 2D vector


## Global functions

### `setClearColor(color)`
Set the clear color of the **myr.js** object. When `clear()` is called, the screen will be cleared using this color.

Parameter | Type | Description
-|-|-
color|[`Color`](#color)|A color which the canvas will be cleared to when `clear()` is called

### `clear()`
Clears the canvas to the currently set clear color

### `free()`
Frees the **myr.js** object and the OpenGL objects it maintains. Note that this function does not free objects like [surfaces](#surface) and [shaders](#shader), these must be freed individually.

### `bind()`
Binds the canvas as the current render target. Always bind before rendering.

### `getTransform()`
Return the [transformation](#transform) which is currently on top of the transform stack.

### `push()`
Push the current [transformation](#transform) onto the stack.

### `pop()`
Pop the current [transformation](#transform) from the stack, restoring the last pushed transformation.

### `transform(transform)`
Transform the current [transformation](#transform) by multiplying it with another transformation.

Parameter | Type | Description
-|-|-
transform|[`Transform`](#transform)|A transform to multiply the current transformation with

### `translate(x, y)`
Translate the current transformation.

Parameter | Type | Description
-|-|-
x|`Number`|Horizontal movement
y|`Number`|Vertical movement

### `rotate(angle)`
Rotate the current transformation.

Parameter | Type | Description
-|-|-
angle|`Number`|Angle in radians

### `shear(x, y)`
Shear the current transformation.

Parameter | Type | Description
-|-|-
x|`Number`|Horizontal shear
y|`Number`|Vertical shear

### `scale(x, y)`
Scale the current transformation

Parameter | Type | Description
-|-|-
x|`Number`|Horizontal scale
y|`Number`|Vertical scale

## Surface

## Shader

## Transform

## Color

## Vector