<template>
    <div class="InputCompoonent">
        <label for="">
            {{label}}
            <input>
        </label>
        
    </div>
</template>
<script>
    // add name property to input and props and see what happens:
    export default {
        props: {
            label: '',
        }
    }
</script>