---
title: Switch
---

# Switch

> Switch between two opposing states

> <CarbonAds />

---

<a href="https://github.com/oruga-ui/oruga/edit/develop/packages/docs/../oruga-next/src/components/switch/examples/Switch.md" class="docgen-edit-link">edit on github</a>

## Examples

### Base

::: demo
<template>
<section>
<o-field>
<o-switch>Default</o-switch>
</o-field>
<o-field>
<o-switch v-model="isSwitched">
{{ isSwitched }}
</o-switch>
</o-field>
<o-field>
<o-switch v-model="isSwitchedCustom"
                true-value="Yes"
                false-value="No">
{{ isSwitchedCustom }}
</o-switch>
</o-field>
<o-field>
<o-switch disabled>Disabled</o-switch>
</o-field>
</section>
</template>

<script>
export default {
    data() {
        return {
            isSwitched: false,
            isSwitchedCustom: 'Yes'
        }
    }
}
</script>

:::

### Variants

::: demo
<template>
<section>
<o-field>
<o-switch :value="true">
Default
</o-switch>
</o-field>
<o-field>
<o-switch :value="true"
            variant="info">
Info
</o-switch>
</o-field>
<o-field>
<o-switch :value="true"
            variant="success">
Success
</o-switch>
</o-field>
<o-field>
<o-switch :value="true"
            variant="danger">
Danger
</o-switch>
</o-field>
<o-field>
<o-switch :value="true"
            variant="warning">
Warning
</o-switch>
</o-field>
</section>
</template>

<script>
export default {
}
</script>

:::

### Sizes

::: demo
<template>
<section>
<o-field>
<o-switch size="small">Small</o-switch>
</o-field>
<o-field>
<o-switch>Default</o-switch>
</o-field>
<o-field>
<o-switch size="medium">Medium</o-switch>
</o-field>
<o-field>
<o-switch size="large">Large</o-switch>
</o-field>
</section>
</template>

<script>
export default {
}
</script>

:::

### Style variants

::: demo
<template>
<section>
<o-field grouped>
<o-switch v-model="isRounded">Rounded</o-switch>
<o-switch v-model="position"
                true-value="left"
                false-value="right">Label on left</o-switch>
</o-field>
<o-field label="Variant">
<o-select expanded v-model="variant" placeholder="Variant">
<option value="null">Default</option>
<option value="primary">Primary</option>
<option value="success">Success</option>
<option value="warning">Warning</option>
<option value="danger">Danger</option>
</o-select>
</o-field>
<o-field label="Passive Variant">
<o-select expanded v-model="passive" placeholder="Passive Variant">
<option value="null">Default</option>
<option value="primary">Primary</option>
<option value="success">Success</option>
<option value="warning">Warning</option>
<option value="danger">Danger</option>
</o-select>
</o-field>
<o-field label="Size">
<o-select expanded v-model="size">
<option value="">Default</option>
<option value="small">small</option>
<option value="medium">medium</option>
<option value="large">large</option>
</o-select>
</o-field>
<o-switch
            :rounded="isRounded"
            :position="position"
            :size="size"
            :variant="variant"
            :passive-variant="passive">Sample</o-switch>
</section>
</template>

<script>
    export default {
        data() {
            return {
                size: '',
                variant: null,
                passive: null,
                isRounded: false,
                position: 'right'
            }
        }
    }
</script>

:::

## Class props

📄 [Full scss file](https://github.com/oruga-ui/oruga/blob/master/packages/oruga/src/scss/components/_switch.scss)

<br />

<br />
<br />

## Props

| Prop name      | Description                                                                         | Type                    | Values                                                                          | Default |
| -------------- | ----------------------------------------------------------------------------------- | ----------------------- | ------------------------------------------------------------------------------- | ------- |
| ariaLabelledby | Accessibility label to establish relationship between the switch and control label' | string                  | -                                                                               |         |
| disabled       |                                                                                     | boolean                 | -                                                                               |         |
| falseValue     | Overrides the returned value when it's not checked                                  | string\|number\|boolean | -                                                                               | false   |
| name           | Name attribute on native checkbox                                                   | string                  | -                                                                               |         |
| nativeValue    | Same as native value                                                                | string\|number\|boolean | -                                                                               |         |
| override       |                                                                                     | boolean                 | -                                                                               |         |
| passiveVariant | Color of the switch when is passive, optional                                       | string                  | `primary`, `info`, `success`, `warning`, `danger`, `and any other custom color` |         |
| position       | Label position                                                                      | string                  | -                                                                               | 'right' |
| required       |                                                                                     | boolean                 | -                                                                               |         |
| rounded        | Rounded style                                                                       | boolean                 | -                                                                               | true    |
| size           | Vertical size of switch, optional                                                   | string                  | `small`, `medium`, `large`                                                      |         |
| trueValue      | Overrides the returned value when it's checked                                      | string\|number\|boolean | -                                                                               | true    |
| v-model        |                                                                                     | string\|number\|boolean | -                                                                               |         |
| variant        | Color of the switch, optional                                                       | string                  | `primary`, `info`, `success`, `warning`, `danger`, `and any other custom color` |         |

## Events

| Event name        | Properties | Description |
| ----------------- | ---------- | ----------- |
| update:modelValue |            |

## Slots

| Name    | Description | Bindings |
| ------- | ----------- | -------- |
| default |             |          |

## Style

| CSS Variable                           | SASS Variable                    | Default                                                                                          |
| -------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------ |
| --oruga-switch-active-background-color | \$switch-active-background-color | \$primary                                                                                        |
| --oruga-switch-action-background       | \$switch-action-background       | #f5f5f5                                                                                          |
| --oruga-switch-background              | \$switch-background              | \$grey-light                                                                                     |
| --oruga-switch-border-radius           | \$switch-border-radius           | \$base-border-radius                                                                             |
| --oruga-switch-box-shadow              | \$switch-box-shadow              | 0 3px 1px 0 rgba(0, 0, 0, 0.05), 0 2px 2px 0 rgba(0, 0, 0, 0.1), 0 3px 3px 0 rgba(0, 0, 0, 0.05) |
| --oruga-switch-disabled-opacity        | \$switch-disabled-opacity        | \$base-disabled-opacity                                                                          |
| --oruga-switch-margin-label            | \$switch-margin-label            | .5em                                                                                             |
| --oruga-switch-padding                 | \$switch-padding                 | 0.2em                                                                                            |
| --oruga-switch-rounded-border-radius   | \$switch-rounded-border-radius   | \$base-rounded-border-radius                                                                     |
| --oruga-switch-width                   | \$switch-width                   | 2.75 \* 1em                                                                                      |