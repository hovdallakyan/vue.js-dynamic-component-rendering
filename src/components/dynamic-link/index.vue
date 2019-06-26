<template>
<div>
    <component :is="component" :data="data" v-if="component" />
    <div>type: {{type}}</div>
</div>
</template>
<script>



export default {
    name: 'dynamic-link',
    props: ['data', 'type'],
    data() {
        return {}
    },
    computed: {
        component() {
            if (!this.type) {
                return null;
            }
            return () => import(`./templates/${this.type}`);;
        },
    }
}
</script>