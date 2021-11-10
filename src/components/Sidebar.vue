<template>
    <div id="sidebar" class="flex-1">
        Render Contacts
        <List :items="reverseList" itemKey="name" type="contact" />
        <button @click="hello">Hello</button>
    </div>
</template>

<script>
import List from '@/components/general/List'

import { reverse } from "lodash";

export default {
    name: "Sidebar",
    components: {
        List
    },
    data() {
        return {
            contacts: [
                { id: 1, name: "John Doe" }, 
                { id: 2, name: "Jane Doe" }
            ]
        }
    },
    methods: {
        hello: debounce(() => {
            console.log('hello');
        }, 1000)
    },
    computed: {
        reverseList() {
            return reverse(this.contacts)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>