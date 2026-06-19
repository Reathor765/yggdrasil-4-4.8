# YggdrasilLineData API

Data object describing how a connection line should be drawn.

---

## Properties

| Type                                | Name                                   | Default    |
| ----------------------------------- | -------------------------------------- | ---------- |
| [LineType](#enum-line-type) {.type} | [line_type](#property-line_type)       | `STRAIGHT` |
| float {.type}                       | [curve_height](#property-curve_height) | `48.0`     |
| int {.type}                         | [segments](#property-segments)         | `16`       |
| bool {.type}                        | [reversed](#property-reversed)         | `false`    |

## Enumerations

### `enum` LineType: { #enum-line-type }

- `LineType` **STRAIGHT** = 0
    - Draws the line as a straight segment between points.
- `LineType` **BEZIER** = 1
    - Draws the line as a quadratic Bézier curve.
- `LineType` **ARC** = 2
    - Draws the line as an arc.

## Property Descriptions

### [LineType](#enum-line-type) line_type <span class="param">=</span> `STRAIGHT` { #property-line_type }
> Determines how the connection line is drawn.

### <span class="type">float</span> curve_height <span class="param">=</span> `48.0` { #property-curve_height }
> Height of the curve used for curved line types.

### <span class="type">int</span> segments <span class="param">=</span> `16` { #property-segments }
> Number of segments used to sample curved line types.

### <span class="type">bool</span> reversed <span class="param">=</span> `false` { #property-reversed }
> Reverses the curve or arc direction.