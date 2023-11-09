<script setup>
 const props = defineProps(['funcaoOperacao'])
</script>

<template>
    <span>{{ props.funcaoOperacao }}</span>
</template>

<style>
span{
  display: block;
  margin-top: 20px;
  font-size: 22px;
  font-weight: bold;
  border: 3px dashed white;
  width: 220px;
  text-align: center;
  padding: 8px;
}
</style>