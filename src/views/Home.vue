<template>

  <div class="home">

    <h2>Tous les produits</h2>

    <v-row>
      <v-col cols="6" sm="3" v-for="produit in produits" :key="produit.id">
        <Produit :produit="produit" />
      </v-col>
    </v-row>

  </div>
</template>

<script>
// @ is an alias to /src
import Produit from '@/components/Produit'

export default {

  components: {
    Produit
  },

  data() {
    return {
      produits: []
    }
  },

  async created () {
    try{
      const produitsInDB = await this.axios.get("http://localhost:3000/produits");
      this.produits = produitsInDB.data;
    }catch(e){
      alert("samarchpa", e)
    }
  },
}
</script>
