<template>
        <div>
                <h1>path: components/custom-vue-ts-decorator</h1>
                <p>Check the code, and your console</p>
        </div>
</template>

<script lang="ts">
import { Vue, Component, Inject } from '@/vue-script'
import { createDecorator } from 'vue-class-component'

const Log = checkYourConsole =>
        createDecorator((comp, key) => {
                if (checkYourConsole) {
                        console.log('Component', comp)
                        console.log('Key', key)
                }
        })

@Component({})
export default class ParentCustomVueTsDecorator extends Vue {
        // Still pondering about more useful examples
        @Log(false) // try passing true and then checking your console
        someData = 'hello'
}
</script>
