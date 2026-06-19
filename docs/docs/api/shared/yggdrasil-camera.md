# `@tool` YggdrasilCamera API

Camera controller for zooming and dragging a tree view viewport within bounds.

---

## Signals

| Name                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------- |
| [zoom_changed](#signal-zoom_changed)(<span class="param">zoom:</span> float, <span class="param">previous_zoom:</span> float) |

## Properties

| Type            | Name                                         | Default         |
| --------------- | -------------------------------------------- | --------------- |
| Control {.type} | [_viewport](#property-_viewport)             | `null`          |
| Rect2 {.type}   | [_bounds](#property-_bounds)                 | `Rect2()`       |
| float {.type}   | [_zoom](#property-_zoom)                     | `1.0`           |
| bool {.type}    | [_dragging](#property-_dragging)             | `false`         |
| Vector2 {.type} | [_last_mouse_pos](#property-_last_mouse_pos) | `Vector2(0, 0)` |

## Methods

| Type         | Name                                                                        |
| ------------ | --------------------------------------------------------------------------- |
| void {.type} | [set_viewport](#set_viewport)(<span class="param">viewport:</span> Control) |
| void {.type} | [set_bounds](#set_bounds)(<span class="param">bounds:</span> Rect2)         |
| void {.type} | [input](#input)(<span class="param">event:</span> InputEvent)               |
| void {.type} | [set_camera_zoom](#set_camera_zoom)(<span class="param">zoom:</span> float) |

## Signal Descriptions

### zoom_changed(<span class="param">zoom:</span> float, <span class="param">previous_zoom:</span> float) { #signal-zoom_changed }
> Emitted when the camera zoom changes.

## Property Descriptions

### <span class="type">Control</span> _viewport <span class="param">=</span> `null` { #property-_viewport }
> Viewport control affected by camera movement and zoom.

### <span class="type">Rect2</span> _bounds <span class="param">=</span> `Rect2()` { #property-_bounds }
> Bounds used to clamp camera movement.

### <span class="type">float</span> _zoom <span class="param">=</span> `1.0` { #property-_zoom }
> Current camera zoom factor.

### <span class="type">bool</span> _dragging <span class="param">=</span> `false` { #property-_dragging }
> Tracks whether middle mouse dragging is active.

### <span class="type">Vector2</span> _last_mouse_pos <span class="param">=</span> `Vector2(0, 0)` { #property-_last_mouse_pos }
> Last recorded mouse position while dragging.

## Method Descriptions

### <span class="type">void</span> set_viewport(<span class="param">viewport:</span> Control) { #set_viewport }
> Sets the viewport control, enables offset transforms on it, and connects resize handling.

### <span class="type">void</span> set_bounds(<span class="param">bounds:</span> Rect2) { #set_bounds }
> Sets the camera movement bounds.

### <span class="void">void</span> input(<span class="param">event:</span> InputEvent) { #input }
> Handles mouse wheel zooming and middle mouse dragging input for the camera.

### <span class="type">void</span> set_camera_zoom(<span class="param">zoom:</span> float) { #set_camera_zoom }
> Sets the camera zoom, updates viewport transform scale and position, clamps the result, and emits `zoom_changed`.