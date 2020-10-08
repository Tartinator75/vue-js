<template>
  <div class="home">
     
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <p>{{myName}}</p>
    <p>{{myAge}} ans</p>
    <p v-if= "isVisible">C'est visible</p>
    <p v-else= "isVisible">Ce n'est pas visible</p>
    <p v-if= "myAge > 40">Je suis vieux</p>
    <p v-else-if= "myAge > 30">Je ne suis pas si vieux</p>
    
    <div class="product__list">
      <div class="product__item" v-for="product in myProducts" v-bind:key="product.index">
        <img v-bind:src='product.img' alt="">
        <h2>{{product.name}}</h2>
        <p>prix: {{product.price}}</p>
      </div>
    </div>
    <p v-html="myRedTitle"></p>
    <p>
      {{ myAge + 10 }}
      {{ myAge > 40 ? "je suis vieux" : "je suis jeune"}}
    </p>
    <button v-on:click="sayMyName(myName)">Say hello</button>
    <p>
      <input type="text" v-model="myName">
    </p>
    <!-- v-once permet de bloquer la reactivité entre le changement dans les input et la variable qui s'affiche -->
    <p v-once>{{myName}}</p>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
  },
  data : function(){
    return{
      myName: "Nicolas",
      myAge: 35,
      myRedTitle: "<strong style='color:red;'> mon tritre en rouge </strong> ",
      myProducts: [
        {name: "product 1", price: "30", img:"https://shop.static.ingka.ikea.com/revamp/corner-sofas_10671.jpg?imwidth=500"},
        {name: "product 2", price: "130", img:"https://shop.static.ingka.ikea.com/revamp/fabric-sofas-with-chaise-longues_47388.jpg?imwidth=500"},
        {name: "product 3", price: "60", img:"https://shop.static.ingka.ikea.com/revamp/modular-fabric-sofas_15358.jpg?imwidth=500"},
      ],
      myInfo: {

      },
      isVisible: true
    }
  },
  methods:{
    sayHello: function(){
      alert('hello !');
    },
    sayMyName: function(name){
      alert(`hello ${name}`);
    }
  }

}
</script>
