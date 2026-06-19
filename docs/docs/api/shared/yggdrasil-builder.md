# `@tool` YggdrasilBuilder API

Builder for configuring and creating a [YggdrasilTreeView](../shared/yggdrasil-tree-view.md) from a [YggdrasilTree](../resources/yggdrasil-tree.md).

---

## Properties

| Type                                                  | Name                                                                         | Default      |
| ----------------------------------------------------- | ---------------------------------------------------------------------------- | ------------ |
| [YggdrasilTree](../resources/yggdrasil-tree.md)       | [_tree](#property-_tree)                                                     | `null`       |
| [YggdrasilTreeView](../shared/yggdrasil-tree-view.md) | [_tree_view](#property-_tree_view)                                           | `null`       |
| Node {.type}                                          | [_parent](#property-_parent)                                                 | `null`       |
| PackedScene {.type}                                   | [_decoration_scene](#property-_decoration_scene)                             | `null`       |
| PackedScene {.type}                                   | [_node_scene](#property-_node_scene)                                         | `null`       |
| PackedScene {.type}                                   | [_line_scene](#property-_line_scene)                                         | `null`       |
| PackedScene {.type}                                   | [_tooltip_scene](#property-_tooltip_scene)                                   | `null`       |
| Callable {.type}                                      | [_tree_version_mismatch_callback](#property-_tree_version_mismatch_callback) | `Callable()` |
| Callable {.type}                                      | [_decoration_created_callback](#property-_decoration_created_callback)       | `Callable()` |
| Callable {.type}                                      | [_node_created_callback](#property-_node_created_callback)                   | `Callable()` |
| Callable {.type}                                      | [_node_allocated_callback](#property-_node_allocated_callback)               | `Callable()` |
| Callable {.type}                                      | [_node_deallocated_callback](#property-_node_deallocated_callback)           | `Callable()` |
| Callable {.type}                                      | [_prefab_created_callback](#property-_prefab_created_callback)               | `Callable()` |
| Callable {.type}                                      | [_line_created_callback](#property-_line_created_callback)                   | `Callable()` |
| Callable {.type}                                      | [_preallocation_check_callback](#property-_preallocation_check_callback)     | `Callable()` |
| Callable {.type}                                      | [_allocation_check_callback](#property-_allocation_check_callback)           | `Callable()` |
| Callable {.type}                                      | [_deallocation_check_callback](#property-_deallocation_check_callback)       | `Callable()` |
| Callable {.type}                                      | [_node_refund_check_callback](#property-_node_refund_check_callback)         | `Callable()` |

## Methods

| Type                                                  | Name                                                                                                             |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [set_parent](#set_parent)(<span class="param">parent:</span> Node)                                               |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [set_decoration_scene](#set_decoration_scene)(<span class="param">decoration_scene:</span> PackedScene)          |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [set_node_scene](#set_node_scene)(<span class="param">node_scene:</span> PackedScene)                            |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [set_line_scene](#set_line_scene)(<span class="param">line_scene:</span> PackedScene)                            |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [set_tooltip_scene](#set_tooltip_scene)(<span class="param">tooltip_scene:</span> PackedScene)                   |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [tree_version_mismatch_callback](#tree_version_mismatch_callback)(<span class="param">callback:</span> Callable) |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [decoration_created_callback](#decoration_created_callback)(<span class="param">callback:</span> Callable)       |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [node_created_callback](#node_created_callback)(<span class="param">callback:</span> Callable)                   |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [node_allocated_callback](#node_allocated_callback)(<span class="param">callback:</span> Callable)               |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [node_deallocated_callback](#node_deallocated_callback)(<span class="param">callback:</span> Callable)           |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [prefab_created_callback](#prefab_created_callback)(<span class="param">callback:</span> Callable)               |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [line_created_callback](#line_created_callback)(<span class="param">callback:</span> Callable)                   |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [preallocation_check_callback](#preallocation_check_callback)(<span class="param">callback:</span> Callable)     |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [allocation_check_callback](#allocation_check_callback)(<span class="param">callback:</span> Callable)           |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [deallocation_check_callback](#deallocation_check_callback)(<span class="param">callback:</span> Callable)       |
| [YggdrasilBuilder](../shared/yggdrasil-builder.md)    | [node_refund_check_callback](#node_refund_check_callback)(<span class="param">callback:</span> Callable)         |
| [YggdrasilTreeView](../shared/yggdrasil-tree-view.md) | [build](#build)()                                                                                                |

## Property Descriptions

### <span class="type">YggdrasilTree</span> _tree <span class="param">=</span> `null` { #property-_tree }
> Tree resource used to build the tree view.

### <span class="type">YggdrasilTreeView</span> _tree_view <span class="param">=</span> `null` { #property-_tree_view }
> Tree view instance created by the builder.

### <span class="type">Node</span> _parent <span class="param">=</span> `null` { #property-_parent }
> Parent node that receives the built tree view.

### <span class="type">PackedScene</span> _decoration_scene <span class="param">=</span> `null` { #property-_decoration_scene }
> Scene used for created decorations.

### <span class="type">PackedScene</span> _node_scene <span class="param">=</span> `null` { #property-_node_scene }
> Scene used for created nodes.

### <span class="type">PackedScene</span> _line_scene <span class="param">=</span> `null` { #property-_line_scene }
> Scene used for created lines.

### <span class="type">PackedScene</span> _tooltip_scene <span class="param">=</span> `null` { #property-_tooltip_scene }
> Scene used for created tooltips.

### <span class="type">Callable</span> _tree_version_mismatch_callback <span class="param">=</span> `Callable()` { #property-_tree_version_mismatch_callback }
> Callback connected to `tree_version_mismatch`.

### <span class="type">Callable</span> _decoration_created_callback <span class="param">=</span> `Callable()` { #property-_decoration_created_callback }
> Callback connected to `decoration_created`.

### <span class="type">Callable</span> _node_created_callback <span class="param">=</span> `Callable()` { #property-_node_created_callback }
> Callback connected to `node_created`.

### <span class="type">Callable</span> _node_allocated_callback <span class="param">=</span> `Callable()` { #property-_node_allocated_callback }
> Callback connected to `node_allocated`.

### <span class="type">Callable</span> _node_deallocated_callback <span class="param">=</span> `Callable()` { #property-_node_deallocated_callback }
> Callback connected to `node_deallocated`.

### <span class="type">Callable</span> _prefab_created_callback <span class="param">=</span> `Callable()` { #property-_prefab_created_callback }
> Callback connected to `prefab_created`.

### <span class="type">Callable</span> _line_created_callback <span class="param">=</span> `Callable()` { #property-_line_created_callback }
> Callback connected to `line_created`.

### <span class="type">Callable</span> _preallocation_check_callback <span class="param">=</span> `Callable()` { #property-_preallocation_check_callback }
> Callback assigned to allocation service preallocation checks.

### <span class="type">Callable</span> _allocation_check_callback <span class="param">=</span> `Callable()` { #property-_allocation_check_callback }
> Callback assigned to allocation service allocation checks.

### <span class="type">Callable</span> _deallocation_check_callback <span class="param">=</span> `Callable()` { #property-_deallocation_check_callback }
> Callback assigned to allocation service deallocation checks.

### <span class="type">Callable</span> _node_refund_check_callback <span class="param">=</span> `Callable()` { #property-_node_refund_check_callback }
> Callback assigned to allocation service refund checks.

## Method Descriptions

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) set_parent(<span class="param">parent:</span> Node) { #set_parent }
> Sets the parent node that will receive the built tree view and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) set_decoration_scene(<span class="param">decoration_scene:</span> PackedScene) { #set_decoration_scene }
> Sets the scene used for created decorations and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) set_node_scene(<span class="param">node_scene:</span> PackedScene) { #set_node_scene }
> Sets the scene used for created nodes and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) set_line_scene(<span class="param">line_scene:</span> PackedScene) { #set_line_scene }
> Sets the scene used for created lines and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) set_tooltip_scene(<span class="param">tooltip_scene:</span> PackedScene) { #set_tooltip_scene }
> Sets the scene used for created tooltips and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) tree_version_mismatch_callback(<span class="param">callback:</span> Callable) { #tree_version_mismatch_callback }
> Sets the callback connected to `tree_version_mismatch` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) decoration_created_callback(<span class="param">callback:</span> Callable) { #decoration_created_callback }
> Sets the callback connected to `decoration_created` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) node_created_callback(<span class="param">callback:</span> Callable) { #node_created_callback }
> Sets the callback connected to `node_created` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) node_allocated_callback(<span class="param">callback:</span> Callable) { #node_allocated_callback }
> Sets the callback connected to `node_allocated` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) node_deallocated_callback(<span class="param">callback:</span> Callable) { #node_deallocated_callback }
> Sets the callback connected to `node_deallocated` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) prefab_created_callback(<span class="param">callback:</span> Callable) { #prefab_created_callback }
> Sets the callback connected to `prefab_created` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) line_created_callback(<span class="param">callback:</span> Callable) { #line_created_callback }
> Sets the callback connected to `line_created` and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) preallocation_check_callback(<span class="param">callback:</span> Callable) { #preallocation_check_callback }
> Sets the callback assigned to allocation service preallocation checks and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) allocation_check_callback(<span class="param">callback:</span> Callable) { #allocation_check_callback }
> Sets the callback assigned to allocation service allocation checks and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) deallocation_check_callback(<span class="param">callback:</span> Callable) { #deallocation_check_callback }
> Sets the callback assigned to allocation service deallocation checks and returns the builder.

### [YggdrasilBuilder](../shared/yggdrasil-builder.md) node_refund_check_callback(<span class="param">callback:</span> Callable) { #node_refund_check_callback }
> Sets the callback assigned to allocation service refund checks and returns the builder.

### [YggdrasilTreeView](../shared/yggdrasil-tree-view.md) build() { #build }
> Creates a tree view, connects configured callbacks, adds the tree view to the parent, loads runtime tree state outside the editor, initializes the tree view, applies allocation callbacks, and returns the built tree view.