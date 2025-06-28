<script setup>
const props = defineProps([
    'campo1',
    'campo2',
    'operacao',
])
</script>

<template>
    <form>
        <div class="row">
            <div class="col-5">
                <input type="number" @change="props.campo1" class="form-control" placeholder="0">
            </div>
            <div class="col-2">
                <select class="form-select" @change="props.operacao">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                </select>
            </div>
            <div class="col-5">
                <input type="number" @change="props.campo2" class="form-control" placeholder="0">
            </div>
        </div>
    </form>
</template>