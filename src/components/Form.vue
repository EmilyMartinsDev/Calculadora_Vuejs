<script setup>


const props = defineProps(['valorPrimeiro', 'valorSegundo', 'valorCalculo']);

</script>


<template>
    <form action="">
        <div class="row">
            <div class="col-md-3">
                <input class="form-control" @change="props.valorPrimeiro" type="number"
                    placeholder="Primeiro numero">
            </div>
            <div class="col-md-3">
                <input class="form-control" @change="props.valorSegundo" type="number"
                    placeholder="Segundo numero">
            </div>
            <div class="col-md-6">
                <select @change="props.valorCalculo" class="form-control">
                    <option value="multiplicar">multiplicar</option>
                    <option value="dividir">dividir</option>
                    <option value="somar">somar</option>
                    <option value="subtrair">subtrair</option>
                </select>
            </div>
        </div>
    </form>
</template>