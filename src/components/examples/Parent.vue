<template>
    <div class="col-md-12 col-xs-12 TextComponent">
        <component
            :is="$attrs.withInheritAttrs ? 'WithAttrsChild' : 'WithoutAttrsChild'"
            v-bind="$attrs">
        </component>
    </div>
</template>

<script>
    import WithAttrsChild from './WithAttrsChild'
    import WithoutAttrsChild from './WithoutAttrsChild'
    export default {
        inheritAttrs: false,
        components: {
            WithAttrsChild,
            WithoutAttrsChild
        },
        // // undo this comment and checkout what happens to the withInheritAttrs property.
        // props: {
        //     withInheritAttrs: {
        //         type: Boolean,
        //         default: false
        //     }
        // }
    }
</script>

<style scoped>
    p {
        font-size: 16px;
    }
</style>
