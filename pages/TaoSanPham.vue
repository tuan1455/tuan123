<!-- Please remove this file from your project -->
<template>
 <div class>
  <form @submit.prevent="submit">
   <label>Ten San Pham</label>
   <input v-model="tenSp" type="text" placeholder="TenSp" required>
   <label>Loai San Pham</label>
   <select v-model="selected" required>
  <option v-for=" option in post" :key="option.Id">
    {{ option.TenLoai }}
  </option>
</select>
    <button type="submit">Tao san pham</button>
  </form>
 </div>
</template>

<script>
import axios from "axios";
import fetch from "node-fetch";
export default {
  data(){
    return {
      selected: 1,
      tenSp: "",
      post:[
    {
        Id: 0,
        TenLoai: ""
    },
],
    }
  },
  methods : {
submit(){alert("gdfg")
console.log(this.post);

}
  },
  async fetch() {
    this.post = await fetch("http://localhost:60298/Loais/DsLoai").then(
      (res) => res.json()
    );
  },

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

