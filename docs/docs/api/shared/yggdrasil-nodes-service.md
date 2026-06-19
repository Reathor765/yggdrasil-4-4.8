# `@tool` YggdrasilNodesService API

Service for creating, loading, duplicating, and updating [YggdrasilNodeButton](./yggdrasil-node-button.md) instances for a tree view.

---

## Signals

| Name                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [node_created](#signal-node_created)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                              |
| [node_pressed](#signal-node_pressed)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                              |
| [node_hovered](#signal-node_hovered)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">is_hovered:</span> bool) |

## Properties

| Type                                                                       | Name                       | Default |
| -------------------------------------------------------------------------- | -------------------------- | ------- |
| Dictionary[int, [YggdrasilNodeButton](./yggdrasil-node-button.md)] {.type} | [_nodes](#property-_nodes) | `{}`    |

## Methods

| Type                                              | Name                                                                                                                                                                            |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| void {.type}                                      | [load_tree](#load_tree)(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md))                                                                  |
| void {.type}                                      | [delete_node](#delete_node)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                                 |
| [YggdrasilNodeButton](./yggdrasil-node-button.md) | [create_node](#create_node)(<span class="param">position:</span> Vector2, <span class="param">node_type:</span> [NodeType](../resources/yggdrasil-node.md#enum-node-type))      |
| [YggdrasilNodeButton](./yggdrasil-node-button.md) | [create_from_prefab](#create_from_prefab)(<span class="param">position:</span> Vector2, <span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) |
| [YggdrasilNodeButton](./yggdrasil-node-button.md) | [duplicate_node](#duplicate_node)(<span class="param">original_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                  |
| void {.type}                                      | [on_node_preallocated](#on_node_preallocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                               |
| void {.type}                                      | [on_node_unpreallocated](#on_node_unpreallocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                           |
| void {.type}                                      | [on_node_allocated](#on_node_allocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                     |
| void {.type}                                      | [on_node_deallocated](#on_node_deallocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                 |
| void {.type}                                      | [on_node_refund_added](#on_node_refund_added)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                               |
| void {.type}                                      | [on_node_refund_removed](#on_node_refund_removed)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                           |
| [YggdrasilNodeButton](./yggdrasil-node-button.md) | [get_node](#get_node)(<span class="param">node_id:</span> int)                                                                                                                  |

## Signal Descriptions

### node_created(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_created }
> Emitted when a node button is created.

### node_pressed(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_pressed }
> Emitted when a node button is pressed.

### node_hovered(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">is_hovered:</span> bool) { #signal-node_hovered }
> Emitted when a node button hover state changes.

## Property Descriptions

### <span class="type">Dictionary[int, [YggdrasilNodeButton](./yggdrasil-node-button.md)]</span> _nodes <span class="param">=</span> `{}` { #property-_nodes }
> Maps node ids to created node button instances.

## Method Descriptions

### <span class="type">void</span> load_tree(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #load_tree }
> Loads all nodes from `tree_data` by creating button instances for each stored node resource.

### <span class="type">void</span> delete_node(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #delete_node }
> Removes `node` from the internal node id map.

### [YggdrasilNodeButton](./yggdrasil-node-button.md) create_node(<span class="param">position:</span> Vector2, <span class="param">node_type:</span> [NodeType](../resources/yggdrasil-node.md#enum-node-type)) { #create_node }
> Creates a new node at `position` with `node_type`, adds it to the tree data and node container, connects press handling, emits `node_created`, and returns it.

### [YggdrasilNodeButton](./yggdrasil-node-button.md) create_from_prefab(<span class="param">position:</span> Vector2, <span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) { #create_from_prefab }
> Creates a new node from `prefab` at `position`, copies prefab visuals and data, adds it to the tree, optionally links it back to the prefab by reference id, emits `node_created`, and returns it.

### [YggdrasilNodeButton](./yggdrasil-node-button.md) duplicate_node(<span class="param">original_node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #duplicate_node }
> Duplicates `original_node` into a new node with a new id, copied visuals and attributes, offset position, optional prefab linkage, emits `node_created`, and returns it.

### <span class="type">void</span> on_node_preallocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_preallocated }
> Updates `node` and its neighbors after the node becomes preallocated.

### <span class="type">void</span> on_node_unpreallocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_unpreallocated }
> Updates `node` and its neighbors after the node is removed from the preallocated state.

### <span class="type">void</span> on_node_allocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_allocated }
> Updates `node` and its neighbors after the node becomes allocated.

### <span class="type">void</span> on_node_deallocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_deallocated }
> Updates `node` and its neighbors after the node becomes deallocated.

### <span class="type">void</span> on_node_refund_added(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_refund_added }
> Updates `node` and its neighbors after the node is staged for refund.

### <span class="type">void</span> on_node_refund_removed(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_refund_removed }
> Updates `node` and its neighbors after the node is removed from refund staging.

### [YggdrasilNodeButton](./yggdrasil-node-button.md) get_node(<span class="param">node_id:</span> int) { #get_node }
> Returns the node button for `node_id`, or `null` if it is not found.