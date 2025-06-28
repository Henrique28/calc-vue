<script setup>
    const props = defineProps([
        'resultado'
    ])
</script>

<template>
    <div class="p-5 my-4 bg-light rounded-3">
        <strong>Resultado:</strong> {{ resultado }}
    </div>
</template>