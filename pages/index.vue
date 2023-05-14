<template>
  <div>
    <h1>Strona główna</h1>
    <ClassComp :name="pOla.name" :age="pOla.age"/>
  </div>
</template>

<script>
import Customer from '../components/models/customer'
import TopNav from '~/components/TopNav.vue';
import ClassComp from '~/components/ClassComp.vue';
export default {
  name: 'IndexPage',
  components: { TopNav, ClassComp },
  data(){
    return{
      pOla:''
    }
  },
  created(){
    this.pOla=this.person('Ola', '12', 89)
    console.log( this.pOla);
  },
  methods:{
    person(name,salary,age){
      return new Customer(name,salary,age);

    }
  }
}
</script>

<style scoped>

</style>
