<template>
  <section>
    <o-field>
      <o-slider v-model="numbers" :min="1" :max="15" :step="0.5" ticks>
      </o-slider>
    </o-field>

    <o-field>
      <o-slider
        v-model="numbers2"
        variant="danger"
        :min="-2"
        :max="8"
        :step="2"
      >
      </o-slider>
    </o-field>
  </section>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup() {
    const numbers = ref([2, 5])
    const numbers2 = ref([2, 6])

    return {
      numbers,
      numbers2
    }
  }
})
</script>
