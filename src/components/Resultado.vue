
<script setup>

const props = defineProps(['geraResultado'])

</script>

<template>
    <div  class="p-3 bg-success mt-5 display-4 text-center text-light">
      <span>Resultado:</span>
    <span>{{ props.geraResultado }}</span>
    </div>
</template>