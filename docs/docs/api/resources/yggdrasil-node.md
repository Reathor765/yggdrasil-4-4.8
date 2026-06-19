# YggdrasilNode API

Resource that stores node data, visuals, position, connections, and attributes.

---

## Properties

| Type                                                                           | Name                                                 | Default         |
| ------------------------------------------------------------------------------ | ---------------------------------------------------- | --------------- |
| bool {.type}                                                                   | [is_root](#property-is_root)                         | `false`         |
| String {.type}                                                                 | [reference_id](#property-reference_id)               | `""`            |
| int {.type}                                                                    | [id](#property-id)                                   | `0`             |
| String {.type}                                                                 | [name](#property-name)                               | `""`            |
| String {.type}                                                                 | [description](#property-description)                 | `""`            |
| [NodeType](#enum-node-type) {.type}                                            | [type](#property-type)                               | `SMALL`         |
| Texture2D {.type}                                                              | [icon](#property-icon)                               | `null`          |
| Texture2D {.type}                                                              | [border_normal](#property-border_normal)             | `null`          |
| Texture2D {.type}                                                              | [border_intermediate](#property-border_intermediate) | `null`          |
| Texture2D {.type}                                                              | [border_active](#property-border_active)             | `null`          |
| Vector2 {.type}                                                                | [position](#property-position)                       | `Vector2(0, 0)` |
| Dictionary[int, [YggdrasilLineData](../shared/yggdrasil-line-data.md)] {.type} | [line_data](#property-line_data)                     | `{}`            |
| Array[int] {.type}                                                             | [out_nodes](#property-out_nodes)                     | `[]`            |
| Array[int] {.type}                                                             | [in_nodes](#property-in_nodes)                       | `[]`            |
| Dictionary[String, Array] {.type}                                              | [attributes](#property-attributes)                   | `{}`            |
| bool {.type}                                                                   | [locked](#property-locked)                           | `false`         |

## Methods

| Type          | Name                                                                                         |
| ------------- | -------------------------------------------------------------------------------------------- |
| Array {.type} | [get_attribute_value](#get_attribute_value)(<span class="param">attribute_id:</span> String) |

## Enumerations

### `enum` NodeType: { #enum-node-type }

- `NodeType` **SMALL** = 0
    - TODO
- `NodeType` **MEDIUM** = 1
    - TODO
- `NodeType` **LARGE** = 2
    - TODO
- `NodeType` **DECORATION** = 3
    - TODO

## Property Descriptions

### <span class="type">bool</span> is_root <span class="param">=</span> `false` { #property-is_root }
> TODO

### <span class="type">String</span> reference_id <span class="param">=</span> `""` { #property-reference_id }
> TODO

### <span class="type">int</span> id <span class="param">=</span> `0` { #property-id }
> TODO

### <span class="type">String</span> name <span class="param">=</span> `""` { #property-name }
> TODO

### <span class="type">String</span> description <span class="param">=</span> `""` { #property-description }
> TODO

### <span class="type">NodeType</span> type <span class="param">=</span> `SMALL` { #property-type }
> TODO

### <span class="type">Texture2D</span> icon <span class="param">=</span> `null` { #property-icon }
> TODO

### <span class="type">Texture2D</span> border_normal <span class="param">=</span> `null` { #property-border_normal }
> TODO

### <span class="type">Texture2D</span> border_intermediate <span class="param">=</span> `null` { #property-border_intermediate }
> TODO

### <span class="type">Texture2D</span> border_active <span class="param">=</span> `null` { #property-border_active }
> TODO

### <span class="type">Vector2</span> position <span class="param">=</span> `Vector2(0, 0)` { #property-position }
> TODO

### <span class="type">Dictionary[int, [YggdrasilLineData](../shared/yggdrasil-line-data.md)]</span> line_data <span class="param">=</span> `{}` { #property-line_data }
> Each outgoing connection can have its own line data.

### <span class="type">Array[int]</span> out_nodes <span class="param">=</span> `[]` { #property-out_nodes }
> Connection from this to other nodes.

### <span class="type">Array[int]</span> in_nodes <span class="param">=</span> `[]` { #property-in_nodes }
> Connection from other nodes to this.

### <span class="type">Dictionary[String, Array]</span> attributes <span class="param">=</span> `{}` { #property-attributes }
> TODO

### <span class="type">bool</span> locked <span class="param">=</span> `false` { #property-locked }
> Editor-only property.

## Method Descriptions

### <span class="type">Array</span> get_attribute_value(<span class="param">attribute_id:</span> String) { #get_attribute_value }
> Returns the attribute value array for `attribute_id`, or an empty array if the attribute is not present.