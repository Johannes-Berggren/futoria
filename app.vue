<template>
  <v-container>
    <v-row style="height: 90vh" class="text-center" justify="center" align="center">
      <h1
        class="text-white"
        id="countdown"
      />
    </v-row>
  </v-container>
</template>

<script setup lang="ts">
// Set the date we're counting down to
const countDownDate = new Date(1663959600 * 1000).getTime()

// Update the count down every 1 second
setInterval(function () {
  // Get today's date and time
  const now = new Date().getTime()

  // Find the distance between now and the count down date
  const distance = countDownDate - now

  // Time calculations for days, hours, minutes and seconds
  const days = Math.floor(distance / (1000 * 60 * 60 * 24))
  const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
  const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
  const seconds = Math.floor((distance % (1000 * 60)) / 1000)

  const countdown = document.getElementById('countdown')
  if (countdown) countdown.innerHTML = days + ' : ' + hours + ' : ' + minutes + ' : ' + seconds
}, 1000)
</script>

<style lang="sass">
body
  background-image: url("/futoria.jpg")
  background-size: cover
  background-position: center
  background-color: #000f42

#countdown
  font-size: 100px
</style>
