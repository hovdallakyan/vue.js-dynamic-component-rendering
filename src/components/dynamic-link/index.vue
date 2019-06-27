<template>
<div>
    <component :is="component" :data="data" v-if="component" />
    <div>type: {{type}}</div>
</div>
</template>
<script>
import graph from './templates/graph';
import photo from './templates/photo';
import videos from './templates/videos';

export default {
    name: 'dynamic-link',
    props: ['data', 'type'],
    components: {
        graph,
        photo,
        videos
    },
    data() {
        return {}
    },
    computed: {
        component() {
            if (!this.type) {
                return null;
            }
            return this.type;
        },
    }
}
</script>