<template>
  <fancy-button ref="myButton">
    click me!
  </fancy-button>
</template>

<script>
export default {
  name: 'IndexPage',
  loading: {
    color: 'red',
    height: '10px'
  },
  mounted(){
    console.log(this.$refs.myButton);
  }
}  
</script>
