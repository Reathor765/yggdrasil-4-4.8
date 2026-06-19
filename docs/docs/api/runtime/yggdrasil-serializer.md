# YggdrasilSerializer API

Singleton with functions to serialize and deserialize [YggdrasilTreeState](../resources/yggdrasil-tree-state.md)

---

## Methods

| Type         | Name                                                                                                                  |
| ------------ | --------------------------------------------------------------------------------------------------------------------- |
| void {.type} | [save_tree_state](#save_tree_state)(<span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) |
| void {.type} | [load_tree_state](#load_tree_state)(<span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) |

## Method Descriptions

### <span class="type">void</span> save_tree_state(<span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #save_tree_state }
> Serializes [YggdrasilTreeState](../resources/yggdrasil-tree-state.md) from [YggdrasilTree](../resources/yggdrasil-tree.md) into `user://yggdrasil/{uid}.tree` file.

### <span class="type">void</span> load_tree_state(<span class="param">tree:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #load_tree_state }
> Deserializes [YggdrasilTreeState](../resources/yggdrasil-tree-state.md) from `user://yggdrasil/{uid}.tree` file into [YggdrasilTree](../resources/yggdrasil-tree.md).