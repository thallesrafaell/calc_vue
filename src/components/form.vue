<script setup>
    const props = defineProps(['capturaInput1', 'capturaInput2', 'capturaSelect'])
</script>

<template>
    <form>
      <input @keyup="props.capturaInput1" />
      <select @change="props.capturaSelect">
        <option selected></option>
        <option>+</option>
        <option >-</option>
        <option >*</option>
        <option >/</option>

      </select>
      <input @keyup="props.capturaInput2" />
    </form>
</template>

<style>
form{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

input {
  height:  30px;
  width: 80px;
  font-size: 22px;
  color: white;
  background-color: transparent;
  border: none;
  border-bottom: 2px solid white;
  text-align: center;
  outline-color: grey;
}

select{
  background-color: transparent;
  color: white;
  border: none;
  border-bottom: 2px solid white;
  height:  30px;
  padding: 2px;
  outline-color: grey;
  
}

select:focus{
  background-color: grey;
  border: 1px solid white;
}
</style>