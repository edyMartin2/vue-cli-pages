<template>
  <div  v-show="x" @click="selected">
    <div
      class="bg-light border rounded "
      style="width: 100%;min-width: 50px;margin: 0em;height: 2.5em;padding: 4px;margin-top: 30px;">
      <i
        class="typcn typcn-briefcase"
        style="margin-left: 6px;margin-top: 7px; float:left"
      ></i>
      <span style="margin-left:1.5em">{{ name.nombre }}</span>
    </div>
  </div>
</template>
<script>
export default {
  name: "hoster",
  props: {
    name
  },
  computed: {
    x() {
      if (this.name.nombre) {
        return true;
      } else {
        return false;
      }
    }
  },
  methods:{
    selected(){
      this.$store.commit('changeHoster', this.name.nombre)
      this.$store.commit('emailHosterChange', this.name.email)
    }
  }
};
</script>
