<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-earth',
          title: 'Bienvenido a Júpiter',
          to: '/'
        },
        {
          icon: 'mdi-account-circle',
          title: 'Login',
          to: '/login'
        },
        {
          icon: 'mdi-account',
          title: 'Usuarios',
          to: '/usuarios'
        },
        {
          icon: '',
          title: 'Eliminar Usuarios',
          to: '/eliminar_usuarios'
        },
        {
          icon: '',
          title: 'Actualizar Usuarios',
          to: '/actualizar_usuarios'
        },
        {
          icon: 'mdi-calendar',
          title: 'Reservas',
          to: '/reservas'
        },
        {
          icon: '',
          title: 'Eliminar Reservas',
          to: '/eliminar_reservas'
        },
        {
          icon: '',
          title: 'Actualizar Reservas',
          to: '/actualizar_reservas'
        },
        {
          icon: 'mdi-cog',
          title: 'Proyectos',
          to: '/proyectos'
        },
        {
          icon: '',
          title: 'Eliminar Proyectos',
          to: '/eliminar_proyectos'
        },
        {
          icon: '',
          title: 'Actualizar Proyectos',
          to: '/actualizar_proyectos'
        },
        {
          icon: 'mdi-label-multiple',
          title: 'Categorias',
          to: '/categorias'
        },
        {
          icon: '',
          title: 'Eliminar Categorias',
          to: '/eliminar_categorias'
        },
        {
          icon: '',
          title: 'Actualizar Categorias',
          to: '/actualizar_categorias'
        },
        
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Júpiter '
    }
  }
}
</script>
