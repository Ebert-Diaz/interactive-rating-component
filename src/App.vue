<template>
  <main>
    <RatingComponent v-if="activeComponent" @showComponent="handleState"/>
    <SubmitState v-else :rating="rating"/>
  </main>
</template>

<script lang="ts">

import { defineComponent, ref} from 'vue';
import RatingComponent from './components/RatingComponent.vue'
import SubmitState from './components/SubmitState.vue'

export default defineComponent({
  name: 'App',
  components: {
    RatingComponent,
    SubmitState
  },
  setup(){
    let activeComponent = ref('true')
    let rating = ref('0')

    const handleState = (data:string) => {
      activeComponent.value = data[0]
      rating.value =  data[1]
      console.log(activeComponent.value)
    } 

    console.log(rating.value)
    return{ activeComponent, handleState, rating }
  }
});

</script>

<style>
body {
  background-color: hsl(216, 12%, 8%);
  font-size: 15px;
  margin: 0;
  padding: 0;
}

main {
	height: 100vh;
	display: flex;

	align-items: center;
	justify-content: center;
}
</style>
