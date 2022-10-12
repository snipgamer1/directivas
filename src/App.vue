<template>
  <div>
    <h1>Directivas</h1>
    <hr />

    <span v-text="title"></span>
    <h1> {{ title }} </h1>
    
    <hr />
    <h1>v-html></h1>
    <div v-html="html"></div>

    <hr />
    <h1>v-show</h1>
    <h3>Tu edad es: {{ years }} </h3>
    <h2 v-if="years >=18 && years >0 && years < 100">Mayor de edad</h2>
    <h2 v-else-if="years < 18 && years >0 && years <100">Menor de edad</h2>
    <h2 v-else>Edad Invalida</h2>

    <button  @click="inc">incrementar</button>
    <button  @click="dis">disminuir</button>
    <hr />
    
    <!-- coamndo v-for -->

     <h1>v-for</h1>
    <ul>
      <li> {{ users[0] }} </li>
      <li> {{ users[1] }} </li>
      <li> {{ users[2] }} </li>
      <li> {{ users[3]}} </li>
    </ul>
    <br />
    <ul>
      <li v-for="user in users "> {{user}} </li>
    </ul>
    <br />
    <ul>
      <li v-for="(user, index) in users "> {{index}}: {{ user }} </li>
    </ul>
    <br />
    <ul>
      <li v-for="(user, index) in users "> {{index}}: {{ user}} </li>
    </ul>
    <br />
    <ul>
      <li v-for="(user, index) in  users" :key="index"> {{index}}: {{ user}} </li>
    </ul>
    <br />
    <ul>
      <li v-for="(valor, clave) in u_users " :key="clave"> {{clave}}: {{ valor}} </li>
    </ul>
    <hr />
    <!-- <h1>v-bind</h1> -->
    <img v-bind:src="url" alt="Hay un">  

  </div>

  <!-- Comando v-on -->
  <hr />
  <h1>v-on</h1>
  <div  @dblclick="click" class="counter"> clicks: {{ clicks }} </div>
</template> 

<script>
  export default {
    data: () => ({
      title: 'Hola desde Vue.js3',
      html: '<h3> Soy un H3</h3>',
      years: 0,
      users: ["Moises" , "Jesus", "Ricardo","Medina"], //comando v-for
      u_users:{name: "Yirsis"}, //comando v-for
      clicks: 0,
      url: "https://cdn.svgporn.com/logos/compose-multiplatform.svg",
    }),
    
    methods: {
      inc (){
        this.years++; //comando v-show
      },
      dis (){
        this.years--; //comando v-show
      },
      click (){
        this.clicks++;
      },
    },
  };

</script>

<style scoped>
  div{
    text-align: center;
    margin: 0px 2rem;
  }
  h2{
    color: black;
  }
  .counter{
    background: blue;
    color: black;
    font-weight: bold;
    height: 400px;

  }
</style>