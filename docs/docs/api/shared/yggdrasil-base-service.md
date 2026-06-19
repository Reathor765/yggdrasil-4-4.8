# `@tool` YggdrasilBaseService API

Base service, inherited by services in `YggdrasilTreeView`.

---

## Properties

| Type                                            | Name                               | Default |
| ----------------------------------------------- | ---------------------------------- | ------- |
| [YggdrasilTreeView](./yggdrasil-tree-view.md)   | [_tree_view](#property-_tree_view) | `null`  |
| [YggdrasilTree](../resources/yggdrasil-tree.md) | [_tree_data](#property-_tree_data) | `null`  |
| PackedScene {.type}                             | [_scene](#property-_scene)         | `null`  |

## Methods

| Type         | Name                                                                                                              |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| void {.type} | [set_scene](#set_scene)(<span class="param">scene:</span> PackedScene)                                            |
| void {.type} | [_position](#_position)(<span class="param">object:</span> Control, <span class="param">position:</span> Vector2) |

## Property Descriptions

### [YggdrasilTreeView](./yggdrasil-tree-view.md) _tree_view <span class="param">=</span> `null` { #property-_tree_view }
> TODO

### [YggdrasilTree](../resources/yggdrasil-tree.md) _tree_data <span class="param">=</span> `null` { #property-_tree_data }
> TODO

### <span class="type">PackedScene</span> _scene <span class="param">=</span> `null` { #property-_scene }
> TODO

## Method Descriptions

### <span class="type">void</span> set_scene(<span class="param">scene:</span> PackedScene) { #set_scene }
> Assigns the scene resource used by this service.

### <span class="type">void</span> _position(<span class="param">object:</span> Control, <span class="param">position:</span> Vector2) { #_position }
> Positions `object` around the given tree-space `position` by centering it on that point and offsetting it relative to the tree size.