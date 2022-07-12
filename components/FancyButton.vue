<template>
    <div>
        <button>
            <slot>
                fall-back- is-use slot-is-empty!
            </slot>
        </button>
        <base-layout>
            <template v-slot:[typeOfSlot]="mySlotData">
                <h1>{{typeOfSlot}}</h1>
                <h1 dir="rtl">{{ mySlotData.mySlotDataHeader || mySlotData.mySlotDataFooter}}</h1>
            </template>
        </base-layout>
        <button @click="typeOfSlot='footer'">footer</button>
        <button @click="typeOfSlot='header'">header</button>
        <div class="scoped-slot-container">
            <h2>scoped slot</h2>
            <scoped-slot v-slot="slotProps">
                {{slotProps.text}}
                {{slotProps.count}}
            </scoped-slot>



            <my-component>
                <template #header="headerProps">
                    {{ headerProps.message }}
                </template>
            </my-component>
            <hr>
            <mouse-tracker v-slot="{ on, x, y }">
                mouse is at : {{x}} {{y}}
                <button @click="on">sepcial event for slot</button>
            </mouse-tracker>
            <hr>
        </div>
    </div>
</template>

<script>
import MouseTracker from './MouseTracker.vue'
export default {
  components: { MouseTracker },
    data() {
        return {
            typeOfSlot: 'header'
        }
    }
}
</script>

<style>

    .scoped-slot-container {
        padding: .5%;
        border:1px solid rgba(55, 0, 255, 0.233);
    }

</style>