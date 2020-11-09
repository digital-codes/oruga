<script lang="ts">
import { defineComponent, h, Transition, vShow, withDirectives } from 'vue'

import BaseComponentMixin from '../../utils/BaseComponentMixin'
import config from '../../utils/config'
import { getValueByPath } from '../../utils/helpers'

/**
 * An easy way to toggle what you want
 * @displayName Collapse
 * @example ./examples/Collapse.md
 */
export default defineComponent({
    name: 'OCollapse',
    mixins: [BaseComponentMixin],
    emits: ['update:open', 'open', 'close'],
    props: {
        /**
         * Whether collapse is open or not, use the .sync modifier (Vue 2.x) or v-model:open (Vue 3.x) to make it two-way binding
         */
        open: Boolean,
        /**
         * Custom animation (transition name)
         */
        animation: {
            type: String,
            default: () => {
                return getValueByPath(config, 'collapse.animation', 'fade')
            }
        },
        ariaId: {
            type: String,
            default: ''
        },
        /**
         * Trigger position
         * @values top, bottom
         */
        position: {
            type: String,
            default: 'top',
            validator: (value: string) => {
                return [
                    'top',
                    'bottom'
                ].indexOf(value) > -1
            }
        },
        rootClass: String,
        triggerClass: String,
        contentClass: String
    },
    data() {
        return {
            isOpen: this.open
        }
    },
    watch: {
        open(value) {
            this.isOpen = value
        }
    },
    methods: {
        /**
        * Toggle and emit events
        */
        toggle() {
            this.isOpen = !this.isOpen
            this.$emit('update:open', this.isOpen)
            this.$emit(this.isOpen ? 'open' : 'close')
        }
    },
    render() {
        const trigger = h('div', {
            class: this.computedClass('collapse', 'triggerClass', 'o-collapse-trigger'),
            onClick: { click: this.toggle }
        }, this.$slots.trigger({ open: this.isOpen }) )
        const content = h(Transition, { name: this.animation }, [
            withDirectives(
                h('div', {
                    class: this.computedClass('collapse', 'contentClass', 'o-collapse-content'),
                    'id': this.ariaId, 
                    'aria-expanded': this.isOpen
                }, this.$slots.default()), 
                [ [vShow, this.isOpen] ]
            )
        ])
        return h('div',
            { staticClass: this.computedClass('collapse', 'rootClass', 'o-collapse') },
            this.position === 'top' ? [trigger, content] : [content, trigger])
    }
})
</script>