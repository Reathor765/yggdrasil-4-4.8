# `@tool` YggdrasilPrefabsService API

Service for loading, creating, and resolving [YggdrasilPrefab](../resources/yggdrasil-prefab.md) instances for a tree.

---

## Signals

| Name                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------- |
| [prefab_created](#signal-prefab_created)(<span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) |

## Properties

| Type                                                                                 | Name                                             | Default |
| ------------------------------------------------------------------------------------ | ------------------------------------------------ | ------- |
| Dictionary[[NodeType](../resources/yggdrasil-node.md#enum-node-type), Array] {.type} | [prefabs](#property-prefabs)                     | `{}`    |
| Dictionary[String, [YggdrasilPrefab](../resources/yggdrasil-prefab.md)] {.type}      | [_ref_id_to_prefab](#property-_ref_id_to_prefab) | `{}`    |

## Methods

| Type                                                | Name                                                                                                                                                                    |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| void {.type}                                        | [load_tree](#load_tree)(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md))                                                          |
| [YggdrasilPrefab](../resources/yggdrasil-prefab.md) | [create_prefab](#create_prefab)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">is_copy:</span> bool = `false`) |
| void {.type}                                        | [make_unique](#make_unique)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))                                                         |
| [YggdrasilPrefab](../resources/yggdrasil-prefab.md) | [get_prefab_by_reference_id](#get_prefab_by_reference_id)(<span class="param">reference_id:</span> String)                                                              |

## Signal Descriptions

### prefab_created(<span class="param">prefab:</span> [YggdrasilPrefab](../resources/yggdrasil-prefab.md)) { #signal-prefab_created }
> Emitted when a prefab is loaded or created.

## Property Descriptions

### <span class="type">Dictionary[[NodeType](../resources/yggdrasil-node.md#enum-node-type), Array]</span> prefabs <span class="param">=</span> `{}` { #property-prefabs }
> Maps node types to prefab arrays.

### <span class="type">Dictionary[String, [YggdrasilPrefab](../resources/yggdrasil-prefab.md)]</span> _ref_id_to_prefab <span class="param">=</span> `{}` { #property-_ref_id_to_prefab }
> Maps prefab reference ids to prefab instances.

## Method Descriptions

### <span class="type">void</span> load_tree(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #load_tree }
> Loads prefabs from `tree_data`, builds lookup caches, emits `prefab_created` for each prefab, and reconnects existing nodes to their referenced prefabs.

### [YggdrasilPrefab](../resources/yggdrasil-prefab.md) create_prefab(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md), <span class="param">is_copy:</span> bool = `false`) { #create_prefab }
> Creates a prefab from `node`, optionally assigns a new reference id and links the node to it when `is_copy` is `false`, stores the prefab in tree data and lookup caches, emits `prefab_created`, and returns it.

### <span class="type">void</span> make_unique(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #make_unique }
> Removes prefab linkage from `node`, clearing its reference id and prefab reference.

### [YggdrasilPrefab](../resources/yggdrasil-prefab.md) get_prefab_by_reference_id(<span class="param">reference_id:</span> String) { #get_prefab_by_reference_id }
> Returns the prefab for `reference_id`, or `null` if it is not found.