<template>
  <div>
    <h2>CompositionComponents</h2>
    <p>user: {{ user }}</p>
    <ul>
      <li v-for="(skillPoint, skillName) in skills" :key="skillName">
        {{ skillName }}: {{ skillPoint }}
        <div>
          <button @click="improveSkills(skillName, 1)">
            {{ skillName }}が成長する
          </button>
        </div>
      </li>
    </ul>
    <div>
      <p>{{ count }}</p>
      <button @click="countUp()">countUp</button>
    </div>
  </div>
</template>

<script>
import { reactive, ref } from "vue";

export default {
  props: {
    user: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    console.log(props);

    const skills = reactive({
      vue: 2,
      nuxt: 2,
      php: 2,
    });

    const improveSkills = (skillName, growthRate) => {
      skills[skillName] += growthRate;
    };

    const count = ref(0);

    const countUp = () => {
      count.value += 1;
    };

    return {
      skills,
      improveSkills,
      count,
      countUp,
    };
  },
};
</script>

<style></style>
