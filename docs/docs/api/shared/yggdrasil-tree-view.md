# `@tool` YggdrasilTreeView API

Control for displaying and interacting with a Yggdrasil tree.

---

## Signals

| Name                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [decoration_created](#signal-decoration_created)(<span class="param">decoration:</span> [YggdrasilNode](../resources/yggdrasil-node.md))                                                                                  |
| [node_created](#signal-node_created)(<span class="param">node:</span> [YggdrasilNode](../resources/yggdrasil-node.md))                                                                                                    |
| [node_allocated](#signal-node_allocated)(<span class="param">node:</span> [YggdrasilNode](../resources/yggdrasil-node.md))                                                                                                |
| [node_deallocated](#signal-node_deallocated)(<span class="param">node:</span> [YggdrasilNode](../resources/yggdrasil-node.md))                                                                                            |
| [prefab_created](#signal-prefab_created)(<span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md))                                                                                          |
| [line_created](#signal-line_created)(<span class="param">line:</span> [YggdrasilConnection](../shared/yggdrasil-connection.md), <span class="param">from_node_id:</span> int, <span class="param">to_node_id:</span> int) |
| [tree_version_mismatch](#signal-tree_version_mismatch)(<span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md), <span class="param">saved_version:</span> int)                                   |

## Properties

| Type                                                              | Name                                                     | Default |
| ----------------------------------------------------------------- | -------------------------------------------------------- | ------- |
| Control {.type}                                                   | [main_container](#property-main_container)               | `null`  |
| Control {.type}                                                   | [background_container](#property-background_container)   | `null`  |
| Control {.type}                                                   | [decorations_container](#property-decorations_container) | `null`  |
| Control {.type}                                                   | [lines_container](#property-lines_container)             | `null`  |
| Control {.type}                                                   | [nodes_container](#property-nodes_container)             | `null`  |
| [YggdrasilCamera](./yggdrasil-camera.md)                          | [camera](#property-camera)                               | `null`  |
| [YggdrasilDecorationsService](./yggdrasil-decorations-service.md) | [decorations_service](#property-decorations_service)     | `null`  |
| [YggdrasilNodesService](./yggdrasil-nodes-service.md)             | [nodes_service](#property-nodes_service)                 | `null`  |
| [YggdrasilConnectionsService](./yggdrasil-connections-service.md) | [connections_service](#property-connections_service)     | `null`  |
| [YggdrasilPrefabsService](./yggdrasil-prefabs-service.md)         | [prefabs_service](#property-prefabs_service)             | `null`  |
| [YggdrasilAllocationService](./yggdrasil-allocation-service.md)   | [allocation_service](#property-allocation_service)       | `null`  |
| PackedScene {.type}                                               | [_tooltip_scene](#property-_tooltip_scene)               | `null`  |
| [YggdrasilTooltip](./yggdrasil-tooltip.md)                        | [_tooltip](#property-_tooltip)                           | `null`  |
| [YggdrasilTree](../resources/yggdrasil-tree.md)                   | [_tree_data](#property-_tree_data)                       | `null`  |

## Methods

| Type                | Name                                                                                                                                                                                                                                                                                                                                    |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| void {.type}        | [load_tree](#load_tree)(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md), <span class="param">decoration_scene:</span> PackedScene, <span class="param">node_scene:</span> PackedScene, <span class="param">line_scene:</span> PackedScene, <span class="param">tooltip_scene:</span> PackedScene) |
| Transform2D {.type} | [get_local_space](#get_local_space)()                                                                                                                                                                                                                                                                                                   |
| Vector2 {.type}     | [translate_node_position](#translate_node_position)(<span class="param">node:</span> Control)                                                                                                                                                                                                                                           |
| Vector2 {.type}     | [translate_position](#translate_position)(<span class="param">pos:</span> Vector2)                                                                                                                                                                                                                                                      |
| Vector2 {.type}     | [get_mouse_position_in_tree](#get_mouse_position_in_tree)()                                                                                                                                                                                                                                                                             |

## Signal Descriptions

### decoration_created(<span class="param">decoration:</span> [YggdrasilNode](../resources/yggdrasil-node.md)) { #signal-decoration_created }
> Emitted when a decoration node is created.

### node_created(<span class="param">node:</span> [YggdrasilNode](../resources/yggdrasil-node.md)) { #signal-node_created }
> Emitted when a node is created.

### node_allocated(<span class="param">node:</span> [YggdrasilNode](../resources/yggdrasil-node.md)) { #signal-node_allocated }
> Emitted when a node is allocated.

### node_deallocated(<span class="param">node:</span> [YggdrasilNode](../resources/yggdrasil-node.md)) { #signal-node_deallocated }
> Emitted when a node is deallocated.

### prefab_created(<span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) { #signal-prefab_created }
> Emitted when a prefab is created.

### line_created(<span class="param">line:</span> [YggdrasilConnection](../shared/yggdrasil-connection.md), <span class="param">from_node_id:</span> int, <span class="param">to_node_id:</span> int) { #signal-line_created }
> Emitted when a connection line is created.

### tree_version_mismatch(<span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md), <span class="param">saved_version:</span> int) { #signal-tree_version_mismatch }
> Emitted when the loaded tree state version does not match the tree version.

## Property Descriptions

### <span class="type">Control</span> main_container <span class="param">=</span> `null` { #property-main_container }
> Main container for the whole tree view content.

### <span class="type">Control</span> background_container <span class="param">=</span> `null` { #property-background_container }
> Container for background visuals.

### <span class="type">Control</span> decorations_container <span class="param">=</span> `null` { #property-decorations_container }
> Container for decoration nodes.

### <span class="type">Control</span> lines_container <span class="param">=</span> `null` { #property-lines_container }
> Container for connection lines.

### <span class="type">Control</span> nodes_container <span class="param">=</span> `null` { #property-nodes_container }
> Container for regular nodes.

### <span class="type">YggdrasilCamera</span> camera <span class="param">=</span> `null` { #property-camera }
> Camera used to navigate the tree view.

### <span class="type">YggdrasilDecorationsService</span> decorations_service <span class="param">=</span> `null` { #property-decorations_service }
> Service responsible for loading and creating decorations.

### <span class="type">YggdrasilNodesService</span> nodes_service <span class="param">=</span> `null` { #property-nodes_service }
> Service responsible for loading and creating nodes.

### <span class="type">YggdrasilConnectionsService</span> connections_service <span class="param">=</span> `null` { #property-connections_service }
> Service responsible for loading and updating connections.

### <span class="type">YggdrasilPrefabsService</span> prefabs_service <span class="param">=</span> `null` { #property-prefabs_service }
> Service responsible for loading and creating prefabs.

### <span class="type">YggdrasilAllocationService</span> allocation_service <span class="param">=</span> `null` { #property-allocation_service }
> Service responsible for allocation and refund behavior.

### <span class="type">PackedScene</span> _tooltip_scene <span class="param">=</span> `null` { #property-_tooltip_scene }
> Scene used to instantiate the tooltip.

### <span class="type">YggdrasilTooltip</span> _tooltip <span class="param">=</span> `null` { #property-_tooltip }
> Tooltip instance used to inspect hovered nodes.

### <span class="type">YggdrasilTree</span> _tree_data <span class="param">=</span> `null` { #property-_tree_data }
> Loaded tree data used by this view.

## Method Descriptions

### <span class="type">void</span> load_tree(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md), <span class="param">decoration_scene:</span> PackedScene, <span class="param">node_scene:</span> PackedScene, <span class="param">line_scene:</span> PackedScene, <span class="param">tooltip_scene:</span> PackedScene) { #load_tree }
> Loads `tree_data`, stores `tooltip_scene`, creates internal containers, background, camera, and services, and emits `tree_version_mismatch` if the saved tree state version differs from the tree version.

### <span class="type">Transform2D</span> get_local_space() { #get_local_space }
> Returns the transform that converts from this control space to the tree local space.

### <span class="type">Vector2</span> translate_node_position(<span class="param">node:</span> Control) { #translate_node_position }
> Converts a node control position into tree-space coordinates centered on the tree.

### <span class="type">Vector2</span> translate_position(<span class="param">pos:</span> Vector2) { #translate_position }
> Converts a position into tree-space coordinates centered on the tree.

### <span class="type">Vector2</span> get_mouse_position_in_tree() { #get_mouse_position_in_tree }
> Returns the current mouse position in tree-space coordinates.