# `@tool` YggdrasilTooltip API

Tooltip control for displaying formatted node information.

---

## Properties

| Type                  | Name                     | Default |
| --------------------- | ------------------------ | ------- |
| RichTextLabel {.type} | [label](#property-label) | `null`  |

## Methods

| Type         | Name                                                                                                    |
| ------------ | ------------------------------------------------------------------------------------------------------- |
| void {.type} | [inspect](#inspect)(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) |
| void {.type} | [reset](#reset)()                                                                                       |

## Property Descriptions

### <span class="type">RichTextLabel</span> label <span class="param">=</span> `null` { #property-label }
> Label used to display tooltip text.

## Method Descriptions

### <span class="type">void</span> inspect(<span class="param">node:</span> [YggdrasilNodeButton](./yggdrasil-node-button.md)) { #inspect }
> Fills the tooltip label with formatted text from `node.format_tooltip()`.

### <span class="type">void</span> reset() { #reset }
> Clears the tooltip label text.