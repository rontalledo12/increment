<template>
  <div>
    <div class="row" v-for="(item, index) in data" :key="index">
      <div class="card">
        <center>
          <div class="box">
            <img :src="item.src" />
          </div>
          <span class="p1">{{ item.title }}</span>
          <p class="p2">{{ item.location }}</p>
          <p class="p3">{{ item.description }}</p>
        </center>
        <div v-if="item.withButton == true">
          <a :href="item.link" target="_blank"
            ><button class="button1">Visit</button></a
          >
        </div>
      </div>
    </div>
    <div class="row" v-for="(item, index) in data1" :key="index">
      <div class="card" style="height: 480px">
        <center>
          <div class="box">
            <img :src="item.src" />
          </div>
          <span class="p1">{{ item.name }}</span>
          <p class="p4">{{ item.description }}</p>
        </center>
        <div v-if="item.withButton == true">
          <a :href="item.link" target="_blank"
            ><button class="button1">Visit</button></a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  mounted() {},
  props: ["projects", "navbar", "technologies"],
  data() {
    return {
      data: this.projects,
      data1: this.technologies,
    };
  },
};
</script>
<style scoped lang="scss">
@import "~assets/style/colors.scss";
.row {
  display: inline-block;
  margin: 1% 0.9%;
  width: 23%;
}
.p1 {
  color: $green;
  font-size: 16px !important;
}
.p3 {
  font-size: 14px !important;
}
.p4 {
  font-size: 14px !important;
  padding-top: 20px;
  margin-top: -10px;
}
.card {
  width: 100%;
  height: 380px;
  margin: 1%;
  padding: 5px;
  border-radius: 15px;
  text-align: center;
}
img {
  width: auto;
  height: 220px;
  padding: 15%;
}
.button1 {
  background: linear-gradient(264.22deg, #00b89f 0%, #8f00b5 100%);
  border: none;
  color: $white !important;
  text-align: center;
  font-size: 13px;
  cursor: pointer;
  border-radius: 25px;
  box-shadow: 0px 0px 10px rgba(255, 255, 255, 0.25);
  padding: 10px;
  width: 50%;
  font-size: 81%;
  outline: none;
  margin-bottom: 10px;
}

@media only screen and (max-width: 1200px) {
  .row {
    margin: 1% !important;
    width: 31.33% !important;
  }
}

@media only screen and (max-width: 992px) {
  .row {
    margin: 1% !important;
    width: 48% !important;
  }
}

@media only screen and (max-width: 769px) {
  .card {
    text-align: center;
    height: 420px !important;
  }
  .row {
    margin: 1% !important;
    width: 48% !important;
  }
}

@media only screen and (max-width: 426px) {
  .row {
    margin: 1% !important;
    width: 80% !important;
  }
  .card {
    height: 420px !important;
  }
}
@media only screen and (max-width: 376px) {
  .card {
    height: 450px !important;
  }
}
@media only screen and (max-width: 321px) {
  .card {
    height: 480px !important;
  }
}
</style>