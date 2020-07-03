<template>
    <div>
        <v-card color="red lighten-3" class="mx-auto" max-width="344">
                
            <v-img :src="produit.image" :alt="'Image du produit : ' + produit.nom "></v-img>

            <v-card-title>{{ produit.nom }}</v-card-title>

            <v-card-subtitle>
                {{ produit.marque }}<br>
                {{ produit.description }}<br>
                Prix: {{ produit.prix }}€
            </v-card-subtitle>
        </v-card>
    </div>
</template>

<script>
    export default {
        props: {
            produit: {
                type: Object,
                default: null
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>