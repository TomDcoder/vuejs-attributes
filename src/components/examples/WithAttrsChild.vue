<template>
    <div class="InputCompoonent">
        <label for="">
            {{$attrs.label}}
            <input
                v-bind="$attrs">
        </label>

    </div>
</template>
<script>
    export default {
        inheritAttrs: false
    }
</script>
