<template>
  <doc-wrapper :inspect-class="inspectClass">
    <template #default="s">
      <o-slider v-bind="s" :min="1" :max="10" :value="4">
        <o-slider-tick v-for="val in [1, 2, 3, 4, 5, 6, 7, 8, 9]" :key="val" v-bind="s" :value="val" >
          {{ val }}
        </o-slider-tick>
      </o-slider>
    </template>
  </doc-wrapper>
  <inspector :inspectData="inspectData" :subitem="subitem" @inspect-class="inspectClass = $event"></inspector>
</template>

<script>
export default {
  data() {
    return {
      subitem: "slider-tick",
      inspectClass: {},
      inspectData: [
        {
          class: "rootClass",
          description: "Root class of the element",
        },
        {
          class: "trackClass",
          description: "Class of the slider track",
          action: () => {
          }
        },
        {
          class: "fillClass",
          description: "Class of the filled part of the slider",
          action: () => {
          }
        },
        {
          class: "thumbRoundedClass",
          description: "Class when the slider is rounded",
          properties: ["rounded"],
          action: (cmp) => {
            cmp.data.rounded = true
          }
        },
        {
          class: "thumbDraggingClass",
          description: "Class when the thumb gets dragged",
          warning: "Drag the thumb to see it in action!",
          action: () => {
          }
        },
        {
          class: "disabledClass",
          description: "Class when slider is disabled",
          properties: ["disabled"],
          action: (cmp) => {
            cmp.data.disabled = true;
          }
        },
        {
          class: "thumbWrapperClass",
          description: "Class of the thumb wrapper",
          action: (cmp) => {
            cmp.data.fullScreen = true;
          }
        },
        {
          class: "thumbClass",
          description: "Class of the thumb",
          action: (cmp) => {
            cmp.data.fullScreen = true;
          }
        },
        {
          class: "variantClass",
          description: 'Class of the slider variant',
          properties: ["variant"],
          suffixes: ['primary', 'info', 'warning', 'danger'],
          action: (cmp) => {
            this.position = 'static';
            cmp.data.variant = 'warning';
          }
        },
        {
          class: "tickClass",
          description: "Class of slider tick",
          properties: ["ticks"],
          subitem: true,
        },
        {
          class: "tickHiddenClass",
          description: "Class when slider tick is hidden",
          properties: ["ticks"],
          subitem: true,
        },
        {
          class: "tickLabelClass",
          description: "Class of tick label",
          properties: ["ticks"],
          subitem: true,
        }
      ]
    };
  },
};
</script>
