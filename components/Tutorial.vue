<!-- Please remove this file from your project -->
<template>
  <div>
  <div class="topnav">
    <input @keyup="tttt" type="text" placeholder="Search.."  />
    <a>{{ posts.DSSanPham }}</a>
    <a>{{ test.data.DSSanPham }}</a>
    <button @click="say('bye')">Say bye</button>
    <router-link to="/TaoSanPham">Home</router-link>  </div>
  <div class="main" v-for="item in posts.DSSanPham " :key="item">
  <div><img src="https://upload.wikimedia.org/wikipedia/commons/a/ae/Nuxt_logo.svg" alt="Trulli" width="100" height="50
"></div>
  <div>{{ item.TenSP }}</div>
  <div>{{ item.id }}</div>
  </div></div>
</template>

<script>
import * as url from "url";
import fetch from "node-fetch";
import axios from "axios";

export default {
  methods: {
    async say(message) {
      alert(message);
      this.test = await axios.get("http://localhost:60298/SanPhams/DanhSachSp");
      axios.get("http://localhost:60298/Loais/Create1?tenLoai=tuan123");
      console.log(this.test);
    },
    tttt(){}
  },
  data() {
    return {
      posts: [],
      test: {
        data: [
          {
            DSSanPham: [
              {
                id: [],
                TenSP: [],
                idcategory: [],
              },
            ],
          },
        ],
      },
    };
  },
  async fetch() {
    this.posts = await fetch("http://localhost:60298/SanPhams/DanhSachSp").then(
      (res) => res.json()
    );
  },
};
</script>
<style>

.main {
  width: 75%;
  text-align: center;
  padding: 15px;
  margin-top:19px !important;
  border: 5px solid rgb(9, 218, 9);
  display: block;
  margin: 0 auto;
}
/* Add a black background color to the top navigation bar */
.topnav {
  overflow: hidden;
  background-color: #e9e9e9;
}

/* Style the links inside the navigation bar */
.topnav a {
  float: left;
  display: block;
  color: black;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

/* Change the color of links on hover */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}

/* Style the "active" element to highlight the current page */
.topnav a.active {
  background-color: #2196f3;
  color: white;
}

/* Style the search box inside the navigation bar */
.topnav input[type="text"] {
  float: right;
  padding: 6px;
  border: none;
  margin-top: 8px;
  margin-right: 16px;
  font-size: 17px;
}

/* When the screen is less than 600px wide, stack the links and the search field vertically instead of horizontally */
@media screen and (max-width: 600px) {
  .topnav a,
  .topnav input[type="text"] {
    float: none;
    display: block;
    text-align: left;
    width: 100%;
    margin: 0;
    padding: 14px;
  }
  .topnav input[type="text"] {
    border: 1px solid #ccc;
  }
}
</style>>
