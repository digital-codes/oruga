<template>
  <doc-wrapper :inspect-class="inspectClass">
    <template #default="s">
      <o-tooltip v-bind="s" label="Tooltip!" always>
        <o-button>
          Delayed
        </o-button>
      </o-tooltip>
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
          class: "rootClass",
          description: "Root class of the element",
        },
        {
          class: "contentClass",
          description: "Class of the tooltip content",
          action: () => {
          }
        },
        {
          class: "triggerClass",
          description: "Class of the tooltip trigger",
          action: () => {
          }
        },
        {
          class: "multilineClass",
          description: "Class of the tooltip content when is multiline",
          action: (cmp) => {
            cmp.data.multiline = true
          }
        },
        {
          class: "arrowClass",
          description: "Class of the tooltip arrow",
          action: () => {
          }
        },
        {
          class: "arrowOrderClass",
          description: "Class of the tooltip arrow when its position changes",
          properties: ['position'],
          suffixes: ['top', 'bottom', 'left', 'right'],
          action: (cmp) => {
            cmp.data.position = 'right'
          }
        },
        {
          class: "orderClass",
          description: "Class of the tooltip trigger when its position changes",
          properties: ['position'],
          suffixes: ['top', 'bottom', 'left', 'right'],
          action: (cmp) => {
            cmp.data.position = 'right'
          }
        },
        {
          class: "alwaysClass",
          description: "Class of the tooltip trigger when is always visible",
          action: () => {
          }
        },
        {
          class: "variantClass",
          description: 'Class of the tooltip variant',
          properties: ["variant"],
          suffixes: ['primary', 'info', 'warning', 'danger'],
          action: (cmp) => {
            cmp.data.variant = 'warning';
          }
        }
      ]
    };
  },
};
</script>
