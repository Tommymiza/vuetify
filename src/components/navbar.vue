<template>
  <nav>
    <v-toolbar dark id="navb">
      <v-toolbar-title>
        <span class="white--text font-weight-light" >The</span>
        <span class="red--text font-weight-bold">Continental</span>
        <span class="green--text font-weight-light">Gamer</span>
      </v-toolbar-title>
      <v-btn @click="menu = !menu" fab small>
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-toolbar>
    <v-navigation-drawer v-model="menu" dark absolute>
      <v-list rounded>
        <v-list-item v-for="link in links" :key="link.text" router :to="link.to">
          <v-list-item-action>
            <v-icon>mdi-{{link.icon}}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{link.text}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-group>
          <template v-slot:activator>
            <v-list-item-action>
              <v-icon>mdi-star</v-icon>
            </v-list-item-action>
            <v-list-item-title>Admin</v-list-item-title>
          </template>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data(){
    return{
      menu: false,
      links: [
        {icon:'view-dashboard-outline',text:'Dashboard',to:'/dashboard'},
        {icon:'account-group-outline',text:'Membre',to:'/membre'}
      ]
    }
  }
};
</script>

<style lang="scss">
.v-toolbar__content{
  width: 100%;
  display: flex;
  justify-content: space-between;
}
</style>
