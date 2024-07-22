<template>
  <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    <v-toolbar-title>web page</v-toolbar-title>
      <template v-if="$vuetify.display.mdAndUp"></template>
  
  
  
  <v-navigation-drawer v-model="drawer"
        :location="$vuetify.display.mobile ? 'bottom' : undefined"
        temporary>
    <v-list>
      
      <v-list-item title="Dashboard" style="color: blue;" append-icon="fas fa-dashboard"></v-list-item>
      <v-list-item v-for="item in items" :key="item.text" route :to="item.route" active-class="border">
        <v-list-item-content>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data: () => ({
    drawer:false,
    group: null,
    items: [
      { icon: 'fas fa-user', text: 'user', route: '/user' },
      { icon: 'fas fa-store', text: 'store', route: '/shopping page' },
      { icon: 'fas fa-question' , text:'About Us',route:'/aboutus'},
    ]
  }),
  watch: {
      group () {
        this.drawer = false
      },
    },
}
</script>
