<script setup>
import { computed, onMounted, ref } from 'vue'

const pie = ref(null)
const pieLength = ref(null)

const percentageLabel = computed(() => {
  return `${props.percentage}%`
});

const props = defineProps({
  track: {
    type: String,
    default: 'grey'
  },
  width: {
    type: Number,
    default: 25
  },
  color: {
    type: String,
    default: 'cyan'
  },
  percentage: {
    type: Number,
    default: 0
  },
  linecap: {
    type: String,
    default: 'butt' // butt, round, square
  }
})

onMounted(() => {
  pieLength.value = pie.value.getTotalLength();
})
</script>

<template>
  <div class="pie" style="width:200px; height:200;">
    <div class="percentage">{{ percentageLabel }}</div>
    <svg width="200" height="200">
      <path
        v-if="track"
        ref="track"
        fill="none"
        :stroke="track"
        :stroke-width="`${width}px`"
        d="
          M 50, 100
          a 50,50 0 1,1 100,0
          a 50,50 0 1,1 -100,0
          "
      />
      <path
        ref="pie"
        fill="none"
        :stroke="color"
        :stroke-width="`${width}px`"
        :stroke-dasharray="`${pieLength * percentage / 100} ${pieLength}`"
        :stroke-linecap="linecap"
        d="
          M 50, 100
          a 50,50 0 1,1 100,0
          a 50,50 0 1,1 -100,0
          "
      />
    </svg>
  </div>
</template>

<style>
svg {
  transform: rotate(90deg);
  transform-origin: center;
}

path {
  transition: all 0.5s ease-in-out;
}

.pie {
  position: relative;
}

.percentage {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 1.5rem;
  font-weight: bold;
  color: white;
}
</style>
