<!-- Please remove this file from your project -->
<template>
 <div class>
   <label>Ten San Pham</label>
   <input v-model="tenSp" type="text" placeholder="TenSp">
   <label>Loai San Pham</label>
   <input v-model="tenSp" type="text" placeholder="TenSp">
 </div>
</template>

<script>

export default {
  data() {
    return {
      tenSp: ""
    }
  }
}
</script>
<style>
input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type=submit] {
  width: 100%;
  background-color: #4CAF50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>

