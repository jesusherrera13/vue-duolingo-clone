<template>
  <v-card>
    <v-layout>
      <v-navigation-drawer>
        <v-list>
          <v-list-item title="Navigation drawer"></v-list-item>
        </v-list>
        <v-divider></v-divider>

          <v-list-item
            v-for="(option, i) in menu_options"
            :key="i"
            :value="option"
            active-color="primary"
            :to="option.path"
          >
            <template v-slot:prepend>
              <v-icon 
                :icon="option.icon"
                :color="option.color"
              ></v-icon>
            </template>

            <v-list-item-title v-text="option.text"></v-list-item-title>
          </v-list-item>
      </v-navigation-drawer>


      <v-main style="min-height: 300px;"></v-main>

      <v-navigation-drawer location="right">
        <v-list>
          <v-list-item title="Navigation drawer"></v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-layout>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      menu_options: [
        { text: 'Learn', icon: 'mdi-home', color: 'teal',path: '/learn' },
        { text: 'Practice', icon: 'mdi-weight-lifter', color: 'red', path: '/practice-hub' },
        { text: 'Store', icon: 'mdi-storefront', color: 'purple', path: '/shop' },
        { text: 'Profile', icon: 'mdi-account', color: 'blue', path: '/account' },
      ]
    }
  },
  components: {
  }
}

</script>

<style>

</style>
