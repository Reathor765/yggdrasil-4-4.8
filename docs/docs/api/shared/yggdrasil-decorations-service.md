# `@tool` YggdrasilDecorationsService API

Service for loading and creating decoration nodes in `YggdrasilTreeView`.

---

## Signals

| Name                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------ |
| [decoration_created](#signal-decoration_created)(<span class="param">decoration:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |
| [decoration_pressed](#signal-decoration_pressed)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))       |

## Methods

| Type         | Name                                                                                                                                                                            |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| void {.type} | [load_tree](#load_tree)(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md))                                                                  |
| void {.type} | [create_decoration](#create_decoration)(<span class="param">at_position:</span> Vector2, <span class="param">icon_texture:</span> Texture2D)                                    |
| void {.type} | [create_from_prefab](#create_from_prefab)(<span class="param">position:</span> Vector2, <span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) |

## Signal Descriptions

### decoration_created(<span class="param">decoration:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-decoration_created }
> Emitted when a decoration node is created and added to the decorations container.

### decoration_pressed(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-decoration_pressed }
> Emitted when a decoration node is pressed.

## Method Descriptions

### <span class="type">void</span> load_tree(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #load_tree }
> Loads decoration data from `tree_data.decorations`, instantiates decoration nodes, configures their icons, positions them, adds them to the decorations container, and connects their pressed signal.

### <span class="type">void</span> create_decoration(<span class="param">at_position:</span> Vector2, <span class="param">icon_texture:</span> Texture2D) { #create_decoration }
> Creates a new decoration node at `at_position`, adds it to the decorations container, stores its translated position in tree data, appends its node data to `tree_data.decorations`, and emits `decoration_created`.

### <span class="type">void</span> create_from_prefab(<span class="param">position:</span> Vector2, <span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) { #create_from_prefab }
> Creates a decoration node from `prefab`, optionally associates it with the prefab reference, positions it, adds it to the decorations container, and emits `decoration_created`.