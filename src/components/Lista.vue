<template>
    <div class="container">
      <table class="table">
        <thead>
          <tr>
            <th scope="col">ID</th>
            <th scope="col">Nome</th>
            <th scope="col">Lotes</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="lista in lista" :key="lista.id">
            <td>{{ lista.id }}</td>
            <td>{{ lista.nome }}</td>
            <td>{{ lista.lotes }}</td>
          </tr>
        </tbody>
      </table>
    </div>
</template>

<script>
import axios from "axios";
export default {
  
  name: "Lista",

  data() {
    return {
      lista: [],
    };
  },
  created() {
      axios
        .get("https://api.kleiloes.com.br/tipo-bem/ativos")
        .then((response) => {
          this.lista = response.data;
        });
    },
  methods: {
    
  },
};
</script>