<template>
    <div class="html-clock">
        <div class="time-container hours">{{ hours }}</div>
        <div class="sep">:</div>
        <div class="time-container minutes">{{ minutes }}</div>
        <div class="sep">:</div>
        <div class="time-container seconds">{{ seconds }}</div>

    </div>
</template>

<style lang="postcss">
  .html-clock {
    display: grid;
    grid-template-columns: 3fr 1fr 3fr 1fr 3fr 1.5fr;
    justify-content: center;
    align-items: center;
    width: 500px;
    height: 125px;
  }

  .html-clock > div {
    display: flex;
    justify-content: center;
  }

  .sep {
    animation: blink 1s linear infinite;
  }

  @keyframes blink {
    0%,
    49% {
      opacity: 1;
    }

    50%,
    100% {
      opacity: 0;
    }
  }

  /* Themes */
  .red-lcd {
    color: red;
  }

  .green-lcd {
    color: green;
  }

  .yellow-lcd {
    color: yellow;
  }
</style>

<script>

  export default {
    props: ['theme'],
    data() {
      return {
        hours: '--',
        minutes: '--',
        seconds: '--'
      }
    },
    methods: {
      updateSeconds() {
        this.seconds = new Date().getSeconds();
      },
      updateMinutes() {
        this.minutes = new Date().getMinutes();
      },
      updateHours() {
        this.hours = new Date().getHours();
      },
      updateTime() {
        this.updateSeconds();
        this.updateMinutes();
        this.updateHours();
      }

    },
    computed: {},
    watch: {},
    created() {
      setInterval(() => this.updateTime(), 1000);
    }
  }
</script>
