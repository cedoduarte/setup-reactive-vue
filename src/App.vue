<template>
  <h1 :class="setClass">Ahorros: ${{ ahorros }}</h1>
  <h1 :class="asignaClase()">Ahorros: ${{ ahorros }}</h1>
  <button @click="deposita">Deposita</button>
  <button @click="depositar">Depositar</button>
  <button @click="retira">Retirar</button>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";

const ahorros = ref<number>(500);

const deposita = () => {
  ahorros.value += 100;
}

const depositar = () => {
  ahorros.value += 100;
}

const retira = () => {
  ahorros.value -= 100;
}

const setClass = computed(() => {
  if (ahorros.value >= 500) {
    return "verde";
  }
  return "rojo";
});

const asignaClase = () => {
  if (ahorros.value >= 500) {
    return "verde";
  }
  return "rojo";
}
</script>

<!--
<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  components: {},
  setup() {
    const ahorros = ref<number>(500);
    const deposita = () => {
      ahorros.value += 100;
    }
    return {
      ahorros,
      deposita
    }
  },
  methods: {
    depositar() {
      this.ahorros += 100;
    }
  },
  computed: {

  }
})
</script>
-->

<style scoped>
.verde {
  color: green;
}

.rojo {
  color: red;
}
</style>
