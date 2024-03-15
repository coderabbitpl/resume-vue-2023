<template>
  <div class="resume-skills">
    <h3
      v-motion
      :enter="{ x: 0, opacity: 1 }"
      :initial="{ x: -50, opacity: 0 }"
      class="resume-header"
    >
      {{ title }}
    </h3>
    <ul class="resume-list">
      <template v-for="(skillKey, n) in skills" :key="title + skillKey">
        <li
          v-motion
          :delay="100 + 50 * n"
          :enter="{ x: 0, opacity: 1 }"
          :initial="{ x: -50, opacity: 0 }"
          v-html="$t(`${skillKey}`)"
        ></li>
      </template>
    </ul>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps({
  title: {
    type: String,
    required: true
  },
  skills: {
    type: Array<string>,
    required: true
  }
})
</script>
