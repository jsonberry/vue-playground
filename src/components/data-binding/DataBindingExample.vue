<template>
        <div>
                {{ fooClass }}
                <div v-if="!barClass">Private member being used in the template on a v-if directive</div>
        </div>
</template>


<script lang="ts">
import { Vue, Component } from '@/vue-script'

@Component({
        data() {
                // none of this
                return {
                        // is required
                        fooNonClass: 'this is a public var (non-class-binding)', // when using Vue + TypeScript
                } // here just as example
        }, // All of these can be declared as members of the class, and will be reactive
})
export default class DataBindingExample extends Vue {
        public fooClass = 'this is a public var (class-binding)' // Class members will become part of the Vue instance and be reactive

        // In TS class members are public by default
        // private class members also seem to work in Vue templates just fine, as opposed to Angular + TypeScript
        private barClass = null // In Vue 2.5 and below, be sure to delcare instance state properties if you want them to be reactive
}
</script>
