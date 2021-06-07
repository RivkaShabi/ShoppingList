<template>
  <div class="shopping-list">
  <form class="pure-form" @submit.prevent="handlerSubmit">
    <fieldset>
        <input v-model="input" type="text" placeholder="Please enter item" />
       
        <button type="submit" class="pure-button pure-button-primary">submit</button>
    </fieldset>
</form>
<table class="pure-table">
    <thead>
        <tr>
            <th>#</th>
            <th>Name</th>
          
        </tr>
    </thead>
    <tbody>
        <tr v-for="(item,indexItem) of items" :key="indexItem">
            <td>{{indexItem+1}}</td>
            <td>{{item}}</td>
            
        </tr>
      
    </tbody>
</table>
  </div>
</template>

<script>
export default {
  name: 'shoppingList',
  data(){
      return{
          input:'',
          items:[]
      }
  },
  methods:{
    handlerSubmit(){
    this.items.push(this.input);
    this.input='';
    }
  }
}
</script>

<style scoped>

</style>
