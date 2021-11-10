<template>
    <ul>
        <Item 
        v-for="item in allContacts"
        :key="item.id"
        :class="type">
            {{ item[itemKey] }}
        </Item>
    </ul>
</template>

<script>
    export default {
        name: "List",
        components: {
            Item: {
                name: "Item",
                render(createElement) {
                    return createElement('li', this.$slots.default)
                }
            }
        },
        props: {
            items: {
                type: Array,
                default: () => []
            },
            itemKey: {
                type: String,
                default: () => "value"
            },
            type: {
                type: String,
                default: () => "item"
            }
        },
        computed: {
            allContacts: function() {
                return this.items;
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>