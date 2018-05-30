<template>
  <v-app>
    <v-navigation-drawer app
      v-model = 'drawer'
    >
      <v-list>
        <v-list-tile @click = ''>
          <v-list-tile-action>
            <v-icon>home</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Home</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>


        <v-list-group
                no-action
                value="true"
        >
          <v-list-tile slot="activator">
            <v-list-tile-action>
              <v-icon>category</v-icon>
            </v-list-tile-action>

            <v-list-tile-title>Categories</v-list-tile-title>
          </v-list-tile>
          <v-list-tile
          >
            <v-list-tile-title></v-list-tile-title>
            <v-list-tile-action>
              <v-icon></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>

        <v-list-tile @click = ''>
          <v-list-tile-action>
            <v-icon>shopping_cart</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Your Cart</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>

        <v-list-tile @click = ''>
          <v-list-tile-action>
            <v-icon>info</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>About Us</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>

      </v-list>

    </v-navigation-drawer>
    <v-toolbar app> <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="align-center">
        <span class="title">WS</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-layout row align-center style="width:90%;">
        <v-text-field
                placeholder="Search..."
                single-line
                append-icon="search"
                :append-icon-cb="() => {}"
                color="blue"
                hide-details
        ></v-text-field>
        <v-menu offset-y>
          <v-btn slot="activator" icon>
            <v-badge left>
              <span slot="badge">0</span>
            <v-icon>shopping_cart</v-icon>
            </v-badge>
          </v-btn>
          <v-list>
            <v-list-tile v-for="(cart_item,i) in cart_items" :key="i">
              <v-list-tile-title>{{cart_item.item_name}}</v-list-tile-title>
            </v-list-tile>
          </v-list>
        </v-menu>
      </v-layout>

    </v-toolbar>
    <v-content>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-content>
    <v-footer app></v-footer>
  </v-app>
</template>

<script>
    export default {
        name:'App',
        data:()=>({
            drawer:false,
            cart_items:[{item_id:0,item_name:'No items here'}]

        })

    }
</script>