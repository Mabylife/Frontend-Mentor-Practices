<script setup>
import { ref } from 'vue'

const isOpen = ref(false)

function toggleIsOpen() {
  isOpen.value = !isOpen.value
}
</script>

<template>
  <div class="units-dropdown-container">
    <button @click="toggleIsOpen()">
      <img src="/assets/images/icon-units.svg" alt="setting icon" />
      <span>Units</span>
    </button>
    <div class="dropdownList" v-if="isOpen">
      <button class="option">Switch to Imperial</button>
      <div class="optionsGroup">
        <span class="label">Temperature</span>
        <button class="option">Celsius (°C)</button>
        <button class="option">Fahrenheit (°F)</button>
      </div>
      <div class="separator"></div>
      <div class="optionsGroup">
        <span class="label">Wind Speed</span>
        <button class="option">km/h</button>
        <button class="option">mph</button>
      </div>
      <div class="separator"></div>
      <div class="optionsGroup">
        <span class="label">Precipitation</span>
        <button class="option">Millimeters (mm)</button>
        <button class="option">Inches (in)</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.dropdownList {
  z-index: 10;

  display: flex;
  width: 13.375rem;
  padding: var(--spacing-075, 0.375rem) var(--spacing-100, 0.5rem);
  flex-direction: column;
  align-items: flex-start;
  gap: var(--spacing-050, 0.25rem);

  border-radius: var(--corner-radius-12, 0.75rem);
  border: 1px solid var(--colors-neutral-600, #3c3b5e);
  background: var(--colors-neutral-800, #262540);
  box-shadow: 0 8px 16px 0 rgba(2, 1, 44, 0.32);
}

.optionsGroup {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: var(--spacing-050, 0.25rem);
  align-self: stretch;
}

.option {
  display: flex;
  width: 12.375rem;
  padding: var(--spacing-125, 0.625rem) var(--spacing-100, 0.5rem);
  align-items: center;
  gap: var(--spacing-125, 0.625rem);

  border-radius: var(--corner-radius-8, 0.5rem);

  color: var(--colors-neutral-0, #fff);

  /* text-preset-7 */
  font-family: 'DM Sans';
  font-size: 1rem;
  font-style: normal;
  font-weight: 500;
  line-height: 120%; /* 1.2rem */
  text-align: left;
  justify-content: flex-start;

  flex: 1 0 0;
}

.separator {
  height: 0.0625rem;
  align-self: stretch;
  background: var(--colors-neutral-600, #3c3b5e);
}

.option:hover {
  background: var(--colors-neutral-700, #302f4a);
}

.label {
  margin-bottom: 0.25rem;
  display: flex;
  padding: var(--spacing-075, 0.375rem) var(--spacing-100, 0.5rem) 0 var(--spacing-100, 0.5rem);
  align-items: center;
  gap: 0.625rem;
  align-self: stretch;

  color: var(--colors-neutral-300, #acacb7);

  /* text-preset-8 */
  font-family: 'DM Sans';
  font-size: 0.875rem;
  font-style: normal;
  font-weight: 500;
  line-height: 120%; /* 1.05rem */
}

.units-dropdown-container {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-end;
  gap: 0.62rem;
}

button {
  display: flex;
  padding: var(--spacing-150, 0.75rem) var(--spacing-200, 1rem);
  justify-content: center;
  align-items: center;
  gap: var(--spacing-125, 0.625rem);

  border-radius: 0.5rem;
  background: var(--colors-neutral-800, #262540);

  border: none;
  outline: none;
}

button > span {
  color: var(--colors-neutral-0, #fff);
  text-align: center;

  /* text-preset-7 */
  font-family: 'DM Sans';
  font-size: 1rem;
  font-style: normal;
  font-weight: 500;
  line-height: 120%; /* 1.2rem */
}

@media (max-width: 414px) {
  button {
    display: flex;
    padding: var(--spacing-100, 0.5rem) var(--spacing-125, 0.625rem);
    justify-content: center;
    align-items: center;
    gap: var(--spacing-075, 0.375rem);

    border-radius: var(--corner-radius-6, 0.375rem);
    background: var(--colors-neutral-800, #262540);
  }

  button > span {
    color: var(--colors-neutral-0, #fff);
    text-align: center;
    font-family: 'DM Sans';
    font-size: 0.875rem;
    font-style: normal;
    font-weight: 500;
    line-height: 120%; /* 1.05rem */
  }
}
</style>
