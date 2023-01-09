<template>
<div class="card">
  <div class="startIcon">
    <img src="../assets/icon-star.svg" alt="Start logo" />
  </div>
  <h1 class="title">How did we do?</h1>
  <p class="description">
    Please let us know how we did with your support request. All feedback is
    appreciated to help us improve our offering!
  </p>
  <div class="numbers">
    <button @click="activeBtn = '1'" class="number" :class="{active: activeBtn === '1' }">1</button>
    <button @click="activeBtn = '2'" class="number" :class="{active: activeBtn === '2' }">2</button>
    <button @click="activeBtn = '3'" class="number" :class="{active: activeBtn === '3' }">3</button>
    <button @click="activeBtn = '4'" class="number" :class="{active: activeBtn === '4' }">4</button>
    <button @click="activeBtn = '5'" class="number" :class="{active: activeBtn === '5' }">5</button>
  </div>

  <button @click="handleClick">Submit</button>
</div>
</template>

<script lang="ts" >
   
  import { defineComponent, ref } from 'vue';

  export default defineComponent({
    name: 'RatingComponent',
    emits: ["showComponent"],
    setup(props, { emit }) {

      let activeBtn = ref('')

      const handleClick = () => {
        emit("showComponent", [false, activeBtn.value])
      }
      return {activeBtn, handleClick}
    }
  });


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
  padding: 2.063rem 2.25rem 1.875rem 2rem;
}

.startIcon {
  background-color: hsl(216, 12%, 22%);
  border-radius: 50%;
  width: 3.25rem;
  height: 3.25rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.startIcon img {
  width: 1.125rem;
  height: 1.125rem;
}

.title {
  color: hsl(0, 0%, 100%);
  font-family: "Overpass", sans-serif;
  font-weight: 700;
  margin: 2.188rem 0 1.375rem;
}

.description {
  width: 20.25rem;
  font-family: "Overpass", sans-serif;
  font-weight: 400;
  line-height: 1.5rem;
}

.numbers {
  display: flex;
  flex-direction: row;
  align-items: center;
  width: 21.438rem;
  justify-content: space-between;

  margin: 1.875rem 0;
}

.number {
  background-color: hsl(216, 12%, 22%);
  border-radius: 50%;
  font-family: "Overpass", sans-serif;
  font-weight: 700;
  width: 3.25rem;
  height: 3.25rem;
  display: flex;
  align-items: center;
  justify-content: center;

}

.number:hover {
  background-color: hsl(25, 97%, 53%);
  color: hsl(0, 0%, 100%);
}

.active{
  background-color:hsl(217, 12%, 63%);
}

button {
  border-radius: 2rem;

  width: 21.438rem;
  height: 2.813rem;

  text-transform: uppercase;
  letter-spacing: 0.2rem;

  background-color: hsl(25, 97%, 53%);
  font-family: "Overpass", sans-serif;
  font-weight: 700;
  color: hsl(0, 0%, 100%);

  border-style: solid;
  border-color: hsl(213, 19%, 18%);
}



button:hover {
  color: hsl(25, 97%, 53%);
  background-color: hsl(0, 0%, 100%);

}

@media only screen and (max-width: 600px) {
  .card {
    max-width: 20.375rem;
    max-height: 26rem;
    padding: 1.5rem 1.5rem 2rem 1.5rem;
  }
  .title {
    margin: 1.313rem 0 1.5rem;

  }

  .description {
    width: 18.438rem;
  }

  .numbers {
    width: 18.438rem;
  
    margin: 1.875rem 0 1.438rem;

  }

  button {

    width: 18.438rem;
    height: 2.813rem;

  }
}

</style>