<template>
  <div class="container">
    <header>
      <slot name="header" mySlotDataHeader="سلام خوبی من اسلات دیتای یه اسلات header اسم ا دار هستم عزیزم"></slot>
    </header>
    <main>
      <slot></slot>
    </main>
    <footer>
      <slot name="footer" mySlotDataFooter="سلام خوبی من اسلات دیتای  یه اسلات footer اسم ا دار هستم عزیزم"></slot>
    </footer>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>