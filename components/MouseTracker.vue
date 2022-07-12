<template>
  <div>
    <slot :x="x" :y="y" :on="logger"></slot>
  </div>
</template>

<script>
export default {
    data() {
        return {
            x: 0,
            y: 0
        }
    },
    methods: {
        update(e){
            this.x = e.pageX
            this.y = e.pageY
        },
        logger(e) {
            console.log('HI! this is log from slot');
            console.log(e);
        }
    },
    mounted() {
        window.addEventListener('mousemove', this.update)
    },
    unmounted(){
        window.removeEventListener('mousemove', this.update)
    }
}
</script>

<style>

</style>