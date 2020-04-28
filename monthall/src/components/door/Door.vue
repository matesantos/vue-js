<template>
  <div class="door-area">
        <div class="door-frame" :class="{ selected: selected && !open }">
            <Gift v-if="open && hasGift"/>      
        </div>
        <div class="door" :class="{ open }"
            @click="selected = !selected">
            <div class="number" :class="{ selected }">{{ number }}</div>
            <!-- knob = maçaneta -->
            <div class="knob" :class="{ selected }" @click.stop="open = true"></div>
        </div>
   </div>
</template>

<script>
import Gift from "../gift/Gift";
export default {
    name:'door',
    components: { Gift },
    props: {
        number:{},
        hasGift: { type: Boolean }
    },
    data: function(){
        return {
            open: false,
            selected: false
        }
    }
}
</script>

<style>
:root {
    --door-border: solid 5px brown;
    --selected-border: solid 5px yellow;
}
.door-area{
    position: relative;
    height: 310px;
    width: 200px;
    margin-bottom: 20px;
    border-bottom: 10px solid #AAA;
    font-size: 3em;

    display: flex;
    justify-content: center;
}

.door-frame{
    position: absolute;
    height: 300px;
    width: 180px;

    border-left: var(--door-border);
    border-top: var(--door-border);
    border-right: var(--door-border);

    display: flex;
    justify-content: center;
    align-items: flex-end;
}

.door{
    position: absolute;
    top: 5px;
    height: 295px;
    width: 175px;
    background-color: chocolate;

    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
}

.knob {
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background-color: brown;
    align-self: flex-start;
    margin-top: 60px;
}

.door-frame.selected{
    border-left: var(--selected-border);
    border-top: var(--selected-border);
    border-right: var(--selected-border);
}

.door > .number.selected{
    color: chartreuse;
}

.door > .knob.selected{
    background-color: chartreuse;
}

.door.open {
    background-color: #0007;
}
.door.open .knob{
    display: none;
}

.door.open .number{
    display: none;
}

</style>