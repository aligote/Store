<template>
    <div>
    <v-carousel hide-controls>
        <v-carousel-item v-for="(product,i) in products" :src="item.src" :key="i"></v-carousel-item>
        <v-card-text>ASD</v-card-text>
    </v-carousel>
        <v-container
                fluid
                style="min-height: 0;overflow-x: scroll;"
                grid-list-xs
                grid-list-md
        >
            <v-card flat>
                <v-card-text>
                    <v-container grid-list-sm fluid align-content-center>
                        <v-layout row wrap>

                            <v-flex d-flex xs12 sm6 md3>
                                <a href="product/">
                                    <v-card>
                                    <v-card-title primary class="title">Дънна платка ASUS ROG</v-card-title>
                                        <v-card-media></v-card-media>
                                     </v-card>
                                </a>
                            </v-flex>


                        </v-layout>

                    </v-container>
                </v-card-text>
            </v-card>
        </v-container>
        <v-spacer></v-spacer>
        <v-container>
            <v-list>
                <v-list-tile @click = ''>
                    <v-list-action><img src="" alt="Product"></v-list-action>
                    <v-list-tile-title>Монитор AOC</v-list-tile-title>
                </v-list-tile>
            </v-list>
        </v-container>
    </div>

</template>

<script>
    export default {
        name: "Home",
        data:()=>({
            products:[]
        })
    }
</script>

<style scoped>
a{
    text-decoration: none;
}
</style>