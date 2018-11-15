<template>
  <html-clock theme="red-lcd"></html-clock>
</template>

<style lang="postcss">
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;

    & #App {
      font-size: 2em;
    }
  }
</style>


<script>
import HTMLClock from './components/HTMLClock';
export default {
  components: {
    'html-clock': HTMLClock
  }
}
</script>

