@@ -1,74 +0,0 @@
<template>
  <doc-wrapper :inspect-class="inspectClass">
    <template #default="s">
      <o-radio v-model="s.checkbox" native-value="default" v-bind="s">Radio</o-radio>
    </template>
  </doc-wrapper>
  <inspector :inspectData="inspectData" @inspect-class="inspectClass = $event"></inspector>
</template>

<script>

export default {
  data() {
    return {
      inspectClass: {},
      inspectData: [
        {
          class: 'rootClass',
          description: 'Class of the root element'
        },
        {
          class: 'labelClass',
          description: 'Class of the radio label'
        },
        {
          class: 'checkClass',
          description: 'Class of the native radio element'
        },
        {
          class: 'checkedClass',
          description: 'Class of the root element when checked',
          action: (cmp) => {
            cmp.data.checkbox = 'default';
          }
        },
        {
          class: 'checkCheckedClass',
          description: 'Class of the native radio element when checked',
          action: (cmp) => {
            cmp.data.checkbox = 'default';
          }
        },
        {
          class: 'sizeClass',
          description: 'Class of the radio size',
          properties: ["size"],
          suffixes: ['small', 'medium', 'large'],
          action: (cmp) => {
            cmp.data.size = 'large';
          }
        },
        {
          class: 'disabledClass',
          description: 'Class when radio is disabled',
          properties: ["disabled"],
          action: (cmp) => {
            cmp.data.disabled = true;
          }
        },
        {
          class: 'variantClass',
          description: 'Class of the radio variant',
          properties: ["variant"],
          suffixes: ['primary', 'info', 'warning', 'danger'],
          action: (cmp) => {
            cmp.data.variant = 'warning';
          }
        }
      ]
    }
  }
}
</script>
