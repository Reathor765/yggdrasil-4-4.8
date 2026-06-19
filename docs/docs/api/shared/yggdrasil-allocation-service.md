# `@tool` YggdrasilAllocationService API

Service for allocating, preallocating, refunding, and deallocating nodes in `YggdrasilTreeView`.

---

## Signals

| Name                                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------------------------- |
| [node_preallocated](#signal-node_preallocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))     |
| [node_unpreallocated](#signal-node_unpreallocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |
| [node_allocated](#signal-node_allocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))           |
| [node_deallocated](#signal-node_deallocated)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))       |
| [refund_mode_entered](#signal-refund_mode_entered)()                                                                                   |
| [refund_mode_exited](#signal-refund_mode_exited)()                                                                                     |
| [node_refund_added](#signal-node_refund_added)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md))     |
| [node_refund_removed](#signal-node_refund_removed)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |

## Properties

| Type               | Name                                                 | Default      |
| ------------------ | ---------------------------------------------------- | ------------ |
| Callable {.type}   | [preallocation_check](#property-preallocation_check) | `Callable()` |
| Callable {.type}   | [allocation_check](#property-allocation_check)       | `Callable()` |
| Callable {.type}   | [deallocation_check](#property-deallocation_check)   | `Callable()` |
| Callable {.type}   | [refund_check](#property-refund_check)               | `Callable()` |
| Array[int] {.type} | [_preallocated_nodes](#property-_preallocated_nodes) | `[]`         |
| Array[int] {.type} | [_refund_nodes](#property-_refund_nodes)             | `[]`         |
| bool {.type}       | [_refund_mode](#property-_refund_mode)               | `false`      |

## Methods

| Type               | Name                                                                                                                    |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| void {.type}       | [load_tree](#load_tree)(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md))          |
| void {.type}       | [on_node_pressed](#on_node_pressed)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |
| void {.type}       | [confirm_preallocations](#confirm_preallocations)()                                                                     |
| void {.type}       | [clear_preallocations](#clear_preallocations)()                                                                         |
| void {.type}       | [enter_refund_mode](#enter_refund_mode)()                                                                               |
| void {.type}       | [exit_refund_mode](#exit_refund_mode)()                                                                                 |
| void {.type}       | [confirm_refund](#confirm_refund)()                                                                                     |
| bool {.type}       | [is_refund_mode](#is_refund_mode)()                                                                                     |
| Array[int] {.type} | [get_refund_nodes](#get_refund_nodes)()                                                                                 |

## Signal Descriptions

### node_preallocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_preallocated }
> Emitted when a node is marked as preallocated.

### node_unpreallocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_unpreallocated }
> Emitted when a node is removed from the preallocated state.

### node_allocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_allocated }
> Emitted when a node becomes allocated.

### node_deallocated(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_deallocated }
> Emitted when a node becomes deallocated.

### refund_mode_entered() { #signal-refund_mode_entered }
> Emitted when refund mode is entered.

### refund_mode_exited() { #signal-refund_mode_exited }
> Emitted when refund mode is exited.

### node_refund_added(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_refund_added }
> Emitted when a node is staged for refund.

### node_refund_removed(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #signal-node_refund_removed }
> Emitted when a node is removed from the refund list.

## Property Descriptions

### <span class="type">Callable</span> preallocation_check <span class="param">=</span> `Callable()` { #property-preallocation_check }
> Optional callback used to validate whether preallocation is allowed.

### <span class="type">Callable</span> allocation_check <span class="param">=</span> `Callable()` { #property-allocation_check }
> Optional callback used to validate whether allocation is allowed.

### <span class="type">Callable</span> deallocation_check <span class="param">=</span> `Callable()` { #property-deallocation_check }
> Optional callback used to validate whether deallocation is allowed.

### <span class="type">Callable</span> refund_check <span class="param">=</span> `Callable()` { #property-refund_check }
> Optional callback used to validate whether refund staging is allowed.

### <span class="type">Array[int]</span> _preallocated_nodes <span class="param">=</span> `[]` { #property-_preallocated_nodes }
> Stores ids of currently preallocated nodes.

### <span class="type">Array[int]</span> _refund_nodes <span class="param">=</span> `[]` { #property-_refund_nodes }
> Stores ids of nodes currently staged for refund.

### <span class="type">bool</span> _refund_mode <span class="param">=</span> `false` { #property-_refund_mode }
> Tracks whether refund mode is active.

## Method Descriptions

### <span class="type">void</span> load_tree(<span class="param">tree_data:</span> [YggdrasilTree](../resources/yggdrasil-tree.md)) { #load_tree }
> Loads allocation state from `tree_data.tree_state.allocated_nodes`, marks matching nodes as allocated, updates their state to active, and emits `node_allocated`.

### <span class="type">void</span> on_node_pressed(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #on_node_pressed }
> Handles node press behavior for allocation, preallocation, refund staging, refund unstaging, or deallocation depending on current tree settings and refund mode.

### <span class="type">void</span> confirm_preallocations() { #confirm_preallocations }
> Converts all preallocated nodes into allocated nodes, emits `node_allocated` for each one, and clears the preallocation list.

### <span class="type">void</span> clear_preallocations() { #clear_preallocations }
> Clears all preallocated nodes, emits `node_unpreallocated` for each one, and empties the preallocation list.

### <span class="type">void</span> enter_refund_mode() { #enter_refund_mode }
> Enables refund mode, clears staged refund nodes, and emits `refund_mode_entered`.

### <span class="type">void</span> exit_refund_mode() { #exit_refund_mode }
> Clears staged refund nodes, emits `node_refund_removed` for each one, disables refund mode, and emits `refund_mode_exited`.

### <span class="type">void</span> confirm_refund() { #confirm_refund }
> Deallocates all nodes staged for refund, clears the refund list, disables refund mode, and emits `refund_mode_exited`.

### <span class="type">bool</span> is_refund_mode() { #is_refund_mode }
> Returns whether refund mode is currently active.

### <span class="type">Array[int]</span> get_refund_nodes() { #get_refund_nodes }
> Returns a duplicate of the current refund node id list.