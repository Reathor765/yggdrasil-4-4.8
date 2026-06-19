# `@tool` YggdrasilLoader API

Singleton that loads [YggdrasilRegistry](../resources/yggdrasil-registry.md) and provides access to registered trees.

---

## Properties

| Type                                                            | Name                                     | Default |
| --------------------------------------------------------------- | ---------------------------------------- | ------- |
| [YggdrasilRegistry](../resources/yggdrasil-registry.md) {.type} | [_registry](#property-_registry)         | `null`  |
| Dictionary[String, String] {.type}                              | [_path_to_tree](#property-_path_to_tree) | `{}`    |

## Methods

| Type                                                    | Name                                                                                                                                                                                                                 |
| ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [YggdrasilRegistry](../resources/yggdrasil-registry.md) | [get_registry](#get_registry)()                                                                                                                                                                                      |
| [YggdrasilTree](../resources/yggdrasil-tree.md)         | [load_tree](#load_tree)(<span class="param">path:</span> String)                                                                                                                                                     |
| void {.type}                                            | [add_tree_to_registry](#add_tree_to_registry)(<span class="param">group:</span> [YggdrasilGroup](../resources/yggdrasil-group.md), <span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) |

## Property Descriptions

### [YggdrasilRegistry](../resources/yggdrasil-registry.md) _registry <span class="param">=</span> `null` { #property-_registry }
> Loaded tree registry.

### <span class="type">Dictionary[String, String]</span> _path_to_tree <span class="param">=</span> `{}` { #property-_path_to_tree }
> Maps lowercase `group/tree` paths to tree resource paths.

## Method Descriptions

### [YggdrasilRegistry](../resources/yggdrasil-registry.md) get_registry() { #get_registry }
> Returns the loaded registry.

### [YggdrasilTree](../resources/yggdrasil-tree.md) load_tree(<span class="param">path:</span> String) { #load_tree }
> Loads a tree by case-insensitive `group/tree` path, returning `null` and pushing an error if the path is not registered or the resource fails to load.

### <span class="type">void</span> add_tree_to_registry(<span class="param">group:</span> [YggdrasilGroup](../resources/yggdrasil-group.md), <span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #add_tree_to_registry }
> Adds a lowercase `group/tree` mapping for `tree.resource_path` to the runtime registry cache.