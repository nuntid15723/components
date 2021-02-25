<template>
  <div id="app">
    <div>
      <b-navbar toggleable="lg" type="dark" variant="Success">
        <router-link to="/">Home</router-link>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav class="ml-auto">
            <router-link to="/About">
              <b-button variant="outline-info" @click="sum">
                <b-icon icon="basket" aria-hidden="ture"></b-icon>
              </b-button>
            </router-link>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <router-view
      :orderData="orderData"
      :user="user"
      @updateOrder="UpUser"
      :tprice="tprice"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      orderData: [
        {
          image:
            "https://cf.shopee.co.th/file/10165b8878e0bf4278ce046c860436c4",
          name: "Gaming Keyboard Feeling RGB ",
          text: "",
          price: 1900,
          tag: "#Shop,#Csmju,#MJU",
        },
        {
          image:
            "https://ae01.alicdn.com/kf/HLB1mrcvae3tHKVjSZSgq6x4QFXak/LED-Light-Gaming-Mouse-1600DPI-USB-Charger-X7.jpg",
          name: "LED-Light-Gaming-Mouse ",
          text: "",
          price: 450,
          tag: "#Shop,#Csmju,#MJU",
        },
        {
          image:
            "https://cf.shopee.co.th/file/3c89bfc7b67d54e1f5911c2ca4000376",
          name: "หูฟังเกมมิ่ง Logitech รุ่น G633s 7.1 Surround",
          text: "",
          price: 2500,
          tag: "#Shop,#Csmju,#MJU",
        },
        {
          image:
            "https://mercular.s3.ap-southeast-1.amazonaws.com/images/products/2020/09/XG32VQR-1.jpg",
          name: "Asus ROG XG32VQR 31.5 Monitor 144Hz ",
          text: "",
          price: 25000,
          tag: "#Shop,#Csmju,#MJU",
        },
        {
          image:
            "https://mercular.s3.ap-southeast-1.amazonaws.com/images/products/2020/10/TORQUE-BLACKWHITE-Case-1.jpg",
          name: "ANTEC TORQUE White Computer Case  ",
          text: "",
          price: 12900,
          tag: "#Shop,#Csmju,#MJU",
        },
        {
          image:
            "https://www.jib.co.th/img_master/product/original/2019061315310834108_1.jpg",
          name: " ASUS ROG STRIX HERO III G531GW-A ",
          text: "",
          price: 32000,
          tag: "#Shop,#Csmju,#MJU",
        },
      ],
      user: [],
      tprice: 0,
    };
  },
  methods: {
    UpUser(value) {
      this.user.push(value);
    },
    sum() {
      this.tprice = 0;
      for (var i = 0; i < this.user.length; i++) {
        this.tprice = this.tprice + this.user[i].Sum;
      }
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
