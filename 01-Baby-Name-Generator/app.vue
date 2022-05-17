<!-- At 1:05 on youtube vid -->

<script setup lang="ts">
// TYPESCRIPT
enum Person {
  CHICK = 'Chick',
  DUDE = 'Dude',
  THEY = 'They',
}

enum Style {
  TRENDY = 'Trendy',
  UNIQUE = 'Unique',
}

enum Length {
  LONG = 'Long',
  ALL = 'All',
  SHORT = 'Short',
}

interface OptionsState {
  person: Person;
  style: Style;
  length: Length;
}

const options = reactive<OptionsState>({
  person: Person.CHICK,
  style: Style.UNIQUE,
  length: Length.SHORT,
});
</script>

<template>
  <div class="page-container">
    <h1>Baby Name Generator</h1>
    <p>Choose your option and click the 'Find Names' button below</p>
    <div class="options-container">
      <div class="option-container">
        <h4>Choose a Person</h4>
        <div class="option-buttons">
          <button
            class="option-btn option-left"
            :class="options.person === Person.DUDE && 'option-active'"
            @click="options.person = Person.DUDE"
          >
            Dude
          </button>
          <button
            class="option-btn"
            :class="options.person === Person.THEY && 'option-active'"
            @click="options.person = Person.THEY"
          >
            They
          </button>
          <button
            class="option-btn option-right"
            :class="options.person === Person.CHICK && 'option-active'"
            @click="options.person = Person.CHICK"
          >
            Chick
          </button>
        </div>
      </div>

      <div class="option-container">
        <h4>Choose Style</h4>
        <div class="option-buttons">
          <button
            class="option-btn option-left"
            :class="options.style === Style.TRENDY && 'option-active'"
            @click="options.style = Style.TRENDY"
          >
            Trendy
          </button>
          <button
            class="option-btn option-right"
            :class="options.style === Style.UNIQUE && 'option-active'"
            @click="options.style = Style.UNIQUE"
          >
            Unique
          </button>
        </div>
      </div>

      <div class="option-container">
        <h4>Choose Length</h4>
        <div class="option-buttons">
          <button
            class="option-btn option-left"
            :class="options.length === Length.LONG && 'option-active'"
          >
            Long
          </button>
          <button
            class="option-btn"
            :class="options.length === Length.ALL && 'option-active'"
          >
            All
          </button>
          <button
            class="option-btn option-right"
            :class="options.length === Length.SHORT && 'option-active'"
          >
            Short
          </button>
        </div>
      </div>
      <!-- <div class="option-container"></div>
      <div class="option-container"></div> -->
    </div>
  </div>
</template>

<style scoped>
.page-container {
  font-family: Arial, Helvetica, sans-serif;
  color: rgb(27, 60, 138);
  max-width: 50rem;
  margin: 0 auto;
  text-align: center;
}

h1 {
  font-size: 3rem;
}

.options-container {
  background-color: rgb(255, 238, 236);
  border-radius: 2rem;
  padding: 1rem;
  width: 95%;
  margin: 0 auto;
  margin-top: 4rem;
  position: relative;
}
.option-container {
  margin-bottom: 2rem;
}

.option-btn {
  background: white;
  outline: 0.15rem solid rgb(249, 87, 89);
  border: none;

  padding: 0.75rem;
  width: 12rem;
  font-size: 1rem;
  color: rgb(27, 60, 138);
  cursor: pointer;
  font-weight: 200px;
}

.option-left {
  border-radius: 1rem 0 0 1rem;
}

.option-right {
  border-radius: 0 1rem 1rem 0;
}

.option-active {
  background-color: rgb(249, 87, 89);
  color: white;
}
</style>
