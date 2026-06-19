# `@tool` YggdrasilConnectionsService API

Service for loading, creating, updating, and refreshing connections between nodes in `YggdrasilTreeView`.

---

## Signals

| Name                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [line_created](#signal-line_created)(<span class="param">line:</span> [YggdrasilConnection](../resources/yggdrasil-connection.md), <span class="param">from_node_id:</span> int, <span class="param">to_node_id:</span> int)   |
| [line_disconnected](#signal-line_disconnected)(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |
| [node_connected](#signal-node_connected)(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node_id:</span> int)                                                  |
| [node_disconnected](#signal-node_disconnected)(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node_id:</span> int)                                            |

## Methods

| Type                       | Name                                                                                                                                                                                                                    |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| void {.type}               | [load_tree](#load_tree)(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md))                                                                                                          |
| void {.type}               | [create_connection](#create_connection)(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |
| PackedVector2Array {.type} | [_bezier_points](#_bezier_points)(<span class="param">segments:</span> int, <span class="param">p0:</span> Vector2, <span class="param">p1:</span> Vector2, <span class="param">p2:</span> Vector2)                     |
| PackedVector2Array {.type} | [_arc_points](#_arc_points)(<span class="param">segments:</span> int, <span class="param">center:</span> Vector2, <span class="param">reversed:</span> bool)                                                            |
| void {.type}               | [update_connected_lines](#update_connected_lines)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                                                   |
| Vector2 {.type}            | [_get_center_position](#_get_center_position)(<span class="param">node:</span> Control)                                                                                                                                 |
| void {.type}               | [on_node_allocation_changed](#on_node_allocation_changed)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                                           |

## Signal Descriptions

### line_created(<span class="param">line:</span> [YggdrasilConnection](../resources/yggdrasil-connection.md), <span class="param">from_node_id:</span> int, <span class="param">to_node_id:</span> int) { #signal-line_created }
> Emitted when a connection line is created.

### line_disconnected(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-line_disconnected }
> Emitted when an existing connection between two nodes is removed.

### node_connected(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node_id:</span> int) { #signal-node_connected }
> Emitted when a node is connected to another node.

### node_disconnected(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node_id:</span> int) { #signal-node_disconnected }
> Emitted when a node is disconnected from another node.

## Method Descriptions

### <span class="type">void</span> load_tree(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #load_tree }
> Loads all stored node connections from `tree_data`, instantiates their line nodes, applies line data, adds them to the lines container, updates visibility based on tree reveal state, and emits connection signals.

### <span class="type">void</span> create_connection(<span class="param">from_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">to_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #create_connection }
> Creates a connection between `from_node` and `to_node`. If the connection already exists, removes it instead and emits disconnection signals.

### <span class="type">PackedVector2Array</span> _bezier_points(<span class="param">segments:</span> int, <span class="param">p0:</span> Vector2, <span class="param">p1:</span> Vector2, <span class="param">p2:</span> Vector2) { #_bezier_points }
> Returns a sampled quadratic Bézier curve point array between `p0` and `p2` using `p1` as the control point.

### <span class="type">PackedVector2Array</span> _arc_points(<span class="param">segments:</span> int, <span class="param">center:</span> Vector2, <span class="param">reversed:</span> bool) { #_arc_points }
> Returns a sampled arc point array around `center` using the specified segment count and direction.

### <span class="type">void</span> update_connected_lines(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #update_connected_lines }
> Rebuilds the geometry of all incoming and outgoing lines connected to `node`.

### <span class="type">Vector2</span> _get_center_position(<span class="param">node:</span> Control) { #_get_center_position }
> Returns the center position of `node` based on its position and size.

### <span class="type">void</span> on_node_allocation_changed(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_allocation_changed }
> Refreshes the visual state of lines connected to `node` after its allocation state changes.