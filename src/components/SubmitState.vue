<template>
<div class="card">
    <div class="thankYou">
      <img src="../assets/illustration-thank-you.svg" alt="" />
    </div>
    <div class="selectOf">You select {{props.rating}} out of 5 </div>
    <h1 class="title">Thank you!</h1>
    <p class="description">
      We appreciate you taking the time to give a rating. If you ever need more support, 
      don’t hesitate to get in touch!
    </p>
  </div>
</template>

<script lang= "ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'SubmitState',
  props: {
    rating: String
  },
  setup(props) {
    return {props}
  }
});
</script>

<style scoped>
  @import url("https://fonts.googleapis.com/css2?family=Overpass:wght@400;700&display=swap");

.card {
  background-color: hsl(213, 19%, 18%);
  border-radius: 1rem;
  color: hsl(217, 12%, 63%);
  font-family: "Overpass", sans-serif;
  font-weight: 400;

  max-width: 25.75rem;
  max-height: 26rem;
  padding: 2.688rem 2.5rem 3.313rem 2.188rem;

  flex-direction: column;
  display: flex;
  align-items: center;
}

.thankYou {
  background-color: hsl(216, 12%, 22%);
  border-radius: 50%;
  width: 10.188rem;
  height: 6.938rem;
  display: flex;
  
  align-items: center;
  justify-content: center;

  margin-bottom: 1.813rem;
}

.selectOf {
  align-items: center;
  border-radius: 1rem;
  color: hsl(25, 97%, 53%);
  display: flex;

  font-family: "Overpass", sans-serif;
  font-weight: 700;

  justify-content: center;

  background-color: hsl(216, 12%, 22%);
  width: 12.25rem;
  height: 2.125rem;

  margin-bottom: 2.313rem;
}

.title {
  color: hsl(0, 0%, 100%);
  font-family: "Overpass", sans-serif;
  font-weight: 700;
  margin: 0;
}

.description {
  width: 21.063rem;
  height: 4.063rem;
  font-family: "Overpass", sans-serif;
  font-weight: 400;
  text-align: center;
  margin-bottom: 0;
  line-height: 1.5rem;
}

@media only screen and (max-width: 600px) {

  .card {
    max-width: 20.313rem;
    max-height: 22.625rem;
    padding: 2.063rem 1.625rem 2.75rem 1.688rem;

  }

  .thankYou {
    margin-bottom: 1.438rem;
  }

  .selectOf {

    width: 10.563rem;
    height: 2.25rem;

    margin-bottom: 1.75rem;
  }

  .description {
    width: 18rem;
    height: 4.063rem;
    margin-bottom: 0;
    
  }
}
</style>