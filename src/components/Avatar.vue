<template>
  <div class="d-inline pointer" :id="name+seed">
    <b-popover placement="topleft" :target="name+seed" triggers="hover click">
      <a :href="person.link" target="_blank">{{fullName}}</a>
    </b-popover>
    <img :src="`src/assets/img/people/${person.image}`" class="round" :width="width"/>
  </div>
</template>

<script>

export default {
  name: "Avatar",
  props: ['person', "size", "name"],
  data() {
    return {
    }
  },
  computed: {
    image(){
      return require();
    },
    width(){
      return this.size || 50;
    },
    fullName(){
      if(typeof name === 'undefined') return "Special Guest";
      return this.name.match(/[A-Z][a-z]+|[0-9]+/g).join(' ')
    },
    seed(){
      return Math.floor(Math.random() * 100)
    }
  }
}
</script>

<style lang="css" scoped>
  .round{
    border-radius:100%;
  }
</style>
