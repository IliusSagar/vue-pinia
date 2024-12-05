<script setup>

import { ref, computed } from 'vue'
import { useCounterStore } from '@/stores/counter';

const storeCounter = useCounterStore()

const count = ref(0)

const increaseCount = () => {
  // console.log('increaseCount')
  count.value++
}

const decreaseCount = () => {
 
  count.value--
}

const oddOreven = computed(() => {
  if(count.value % 2 === 0) return 'even'
  return 'odd'
})

</script>


<template>
  <div class="home">
    <div class="count">
      {{ storeCounter.count }}
    </div>
    <div class="buttons">
      <button @click="storeCounter.decreaseCount">-</button>
      <button @click="storeCounter.increaseCount">+</button>
    </div>
    <hr>
    <div>
      This counter is: {{ oddOreven }}
    </div>
  </div>
</template>

<style>
.count{
  font-size: 60px;
  margin: 20px;
}
.buttons button {
  font-size: 40px;
  margin: 10px;
}
</style>
