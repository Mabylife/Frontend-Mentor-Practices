<script setup>
import DaysDropdown from './Days-dropdown.vue'
import HourlyForecastBlock from './Hourly-forecast-block.vue'
</script>

<template>
  <div class="hourlyForecast-container">
    <div class="top">
      <h5>Hourly forcast</h5>
      <DaysDropdown />
    </div>
    <div class="blocks">
      <HourlyForecastBlock v-for="i in 24" :place="i - 1" />
    </div>
  </div>
</template>

<style scoped>
.hourlyForecast-container {
  max-height: 43.3125rem;
  display: flex;
  width: 24rem;
  padding-top: var(--spacing-300, 1.5rem);
  padding-bottom: var(--spacing-300, 1.5rem);
  flex-direction: column;
  align-items: flex-start;
  gap: var(--spacing-200, 1rem);

  border-radius: var(--corner-radius-20, 1.25rem);
  background: var(--colors-neutral-800, #262540);
}

.blocks {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
  gap: var(--spacing-200, 1rem);
  overflow-y: scroll;
  padding-left: var(--spacing-300, 1.5rem);
  padding-right: var(--spacing-300, 1.5rem);

  scrollbar-color: #302f4a transparent;
}

.blocks::-webkit-scrollbar {
  width: 0.25rem;
}

.blocks::-webkit-scrollbar-thumb {
  border-radius: 0.75rem;
  border: 1px solid #3c3b5e;
  background: #302f4a;
}

.top {
  padding-left: var(--spacing-300, 1.5rem);
  padding-right: var(--spacing-300, 1.5rem);
  display: flex;
  justify-content: space-between;
  height: max-content;
  align-items: center;
  width: 100%;
}

h5 {
  color: var(--colors-neutral-0, #fff);

  max-height: 2.3125rem;
  text-wrap: nowrap;

  /* text-preset-5 */
  font-family: 'DM Sans';
  font-size: 1.25rem;
  font-style: normal;
  font-weight: 600;
  line-height: 120%; /* 1.5rem */
}

@media (max-width: 1440px) {
  .hourlyForecast-container {
    width: 100%;
  }
}
</style>
