<template>
    <button class="button" 
            @click="$emit('onClick', label)"
            :class="{ double, triple, operation }">
            {{ label }}
    </button>
</template>

<script>
export default {
    props:{
        label:{},
        operation:{ type: Boolean },
        double:{ type: Boolean },
        triple:{ type: Boolean }
    }
}
</script>

<style>
:root {
    --bg-button: #F0F0F0;
    --border-button: solid 1px #888;
}

.button {
    font-size: 1.4em;
    background-color: var(--bg-button);
    border:none;
    border-right: var(--border-button);
    border-bottom: var(--border-button);
    outline: none;
}

.button:active{
    background-color: #CCC;
}

.button.double {
    grid-column: span 2;  
}

.button.triple {
    grid-column-start: 1;
    grid-column-end: 4;  
}

.button.operation {
    background-color: #FA8231;
    color: #FFF;
}

.button.operation:active{
    background-color: #FA8231cc;
}
</style>
