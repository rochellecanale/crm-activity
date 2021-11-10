<template>
    <div id="sidebar" class="flex-1">
        Render Contacts
        <List :items="contacts" itemKey="name" type="contact" />
    </div>
</template>

<script>
import List from '@/components/general/List'
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
    }
}
</script>

<style lang="scss" scoped>

</style>