<template>
  <div>
    <slot :text="greetingMessage" :count="1"></slot>
    <slot name="message" messageText= "this named scoped slot"></slot>
  </div>
</template>

<script>
export default {
    data() {
        return {
            greetingMessage: 'hi  and wellcome to my blog'
        }
    }
}
</script>

<style>

</style>