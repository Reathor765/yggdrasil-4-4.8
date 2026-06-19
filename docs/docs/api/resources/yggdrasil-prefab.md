# `@tool` YggdrasilPrefab API

Resource that stores shared prefab data for nodes.

---

## Signals

| Name                                                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [name_changed](#signal-name_changed)(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md))                                                                                                      |
| [description_changed](#signal-description_changed)(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md))                                                                                        |
| [icon_changed](#signal-icon_changed)(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md))                                                                                                      |
| [border_changed](#signal-border_changed)(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md))                                                                                                  |
| [attribute_changed](#signal-attribute_changed)(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md), <span class="param">attribute_id:</span> String, <span class="param">removed:</span> bool) |

## Properties

| Type                                                             | Name                                                 | Default |
| ---------------------------------------------------------------- | ---------------------------------------------------- | ------- |
| String {.type}                                                   | [reference_id](#property-reference_id)               | `""`    |
| String {.type}                                                   | [id](#property-id)                                   | `""`    |
| String {.type}                                                   | [node_name](#property-node_name)                     | `""`    |
| String {.type}                                                   | [description](#property-description)                 | `""`    |
| NodeType {.type}                                                 | [type](#property-type)                               |         |
| Texture2D {.type}                                                | [icon](#property-icon)                               | `null`  |
| Texture2D {.type}                                                | [border_normal](#property-border_normal)             | `null`  |
| Texture2D {.type}                                                | [border_intermediate](#property-border_intermediate) | `null`  |
| Texture2D {.type}                                                | [border_active](#property-border_active)             | `null`  |
| Dictionary[String, Array] {.type}                                | [attributes](#property-attributes)                   | `{}`    |
| Array[[YggdrasilNodeButton](../shared/yggdrasil-node-button.md)] | [nodes](#property-nodes)                             | `[]`    |

## Methods

| Type         | Name                                                                                                                                                                           |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| void {.type} | [add_node](#add_node)(<span class="param">node:</span> [YggdrasilNodeButton](../shared/yggdrasil-node-button.md))                                                              |
| void {.type} | [remove_node](#remove_node)(<span class="param">node:</span> [YggdrasilNodeButton](../shared/yggdrasil-node-button.md))                                                        |
| void {.type} | [set_node_name](#set_node_name)(<span class="param">new_name:</span> String)                                                                                                   |
| void {.type} | [set_description](#set_description)(<span class="param">new_description:</span> String)                                                                                        |
| void {.type} | [set_icon](#set_icon)(<span class="param">new_icon:</span> Texture2D)                                                                                                          |
| void {.type} | [set_border_normal](#set_border_normal)(<span class="param">new_border:</span> Texture2D)                                                                                      |
| void {.type} | [set_border_intermediate](#set_border_intermediate)(<span class="param">new_border:</span> Texture2D)                                                                          |
| void {.type} | [set_border_active](#set_border_active)(<span class="param">new_border:</span> Texture2D)                                                                                      |
| void {.type} | [set_attribute](#set_attribute)(<span class="param">attribute_id:</span> String, <span class="param">values:</span> Array)                                                     |
| void {.type} | [remove_attribute](#remove_attribute)(<span class="param">attribute_id:</span> String)                                                                                         |
| void {.type} | [set_attribute_value](#set_attribute_value)(<span class="param">attribute_id:</span> String, <span class="param">index:</span> int, <span class="param">value:</span> Variant) |

## Signal Descriptions

### name_changed(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md)) { #signal-name_changed }
> Emitted when `node_name` is changed.

### description_changed(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md)) { #signal-description_changed }
> Emitted when `description` is changed.

### icon_changed(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md)) { #signal-icon_changed }
> Emitted when `icon` is changed.

### border_changed(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md)) { #signal-border_changed }
> Emitted when a border texture is changed.

### attribute_changed(<span class="param">prefab:</span> [YggdrasilPrefab](./yggdrasil-prefab.md), <span class="param">attribute_id:</span> String, <span class="param">removed:</span> bool) { #signal-attribute_changed }
> Emitted when an attribute is added, updated, or removed.

## Property Descriptions

### <span class="type">String</span> reference_id <span class="param">=</span> `""` { #property-reference_id }
> If empty then this is a copy, otherwise it is a prefab that shares data with referenced nodes.

### <span class="type">String</span> id <span class="param">=</span> `""` { #property-id }
> TODO

### <span class="type">String</span> node_name <span class="param">=</span> `""` { #property-node_name }
> TODO

### <span class="type">String</span> description <span class="param">=</span> `""` { #property-description }
> TODO

### <span class="type">NodeType</span> type { #property-type }
> TODO

### <span class="type">Texture2D</span> icon <span class="param">=</span> `null` { #property-icon }
> TODO

### <span class="type">Texture2D</span> border_normal <span class="param">=</span> `null` { #property-border_normal }
> TODO

### <span class="type">Texture2D</span> border_intermediate <span class="param">=</span> `null` { #property-border_intermediate }
> TODO

### <span class="type">Texture2D</span> border_active <span class="param">=</span> `null` { #property-border_active }
> TODO

### <span class="type">Dictionary[String, Array]</span> attributes <span class="param">=</span> `{}` { #property-attributes }
> Maps attribute ids to arrays of values.

### <span class="type">Array[[YggdrasilNodeButton](../shared/yggdrasil-node-button.md)]</span> nodes <span class="param">=</span> `[]` { #property-nodes }
> Stores nodes associated with this prefab.

## Method Descriptions

### <span class="type">void</span> add_node(<span class="param">node:</span> [YggdrasilNodeButton](../shared/yggdrasil-node-button.md)) { #add_node }
> Adds `node` to the prefab node list.

### <span class="type">void</span> remove_node(<span class="param">node:</span> [YggdrasilNodeButton](../shared/yggdrasil-node-button.md)) { #remove_node }
> Removes `node` from the prefab node list.

### <span class="type">void</span> set_node_name(<span class="param">new_name:</span> String) { #set_node_name }
> Sets `node_name`, updates `id` using `new_name.to_snake_case()`, and emits `name_changed`.

### <span class="type">void</span> set_description(<span class="param">new_description:</span> String) { #set_description }
> Sets `description` and emits `description_changed`.

### <span class="type">void</span> set_icon(<span class="param">new_icon:</span> Texture2D) { #set_icon }
> Sets `icon` and emits `icon_changed`.

### <span class="type">void</span> set_border_normal(<span class="param">new_border:</span> Texture2D) { #set_border_normal }
> Sets `border_normal` and emits `border_changed`.

### <span class="type">void</span> set_border_intermediate(<span class="param">new_border:</span> Texture2D) { #set_border_intermediate }
> Sets `border_intermediate` and emits `border_changed`.

### <span class="type">void</span> set_border_active(<span class="param">new_border:</span> Texture2D) { #set_border_active }
> Sets `border_active` and emits `border_changed`.

### <span class="type">void</span> set_attribute(<span class="param">attribute_id:</span> String, <span class="param">values:</span> Array) { #set_attribute }
> Sets the value array for `attribute_id` and emits `attribute_changed`.

### <span class="type">void</span> remove_attribute(<span class="param">attribute_id:</span> String) { #remove_attribute }
> Removes `attribute_id` from `attributes` and emits `attribute_changed` with `removed` set to `true`.

### <span class="type">void</span> set_attribute_value(<span class="param">attribute_id:</span> String, <span class="param">index:</span> int, <span class="param">value:</span> Variant) { #set_attribute_value }
> Updates a value at `index` in the attribute array for `attribute_id` and emits `attribute_changed` if the attribute and index are valid. `value` must be of type `int` or `float`.