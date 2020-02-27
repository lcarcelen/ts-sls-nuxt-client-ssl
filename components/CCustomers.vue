<template lang="pug">
  div
    div(v-if='customers.length')
      div(v-for='customer in customers' :key='customer.reason')
        CCard.h-20.flex.justify-content.items-center.mb-6(:class="[ $store.getters.darkIsActive ? 'bg-red-700' : 'bg-green-700']") 
          template(slot='content')
            span 
                nuxt-link.pl-4.text-md.font-mono.text-white(:to='customer.link') {{customer.reason}}
</template>

<script>
import CCard from '~/components/CCard.vue'
export default {
  name: 'CCustomers',
  components: {
    CCard
  },
  data() {
    return {
      customers: [
        {
          reason: '1.) Inyección HTML',
          link: '/vulnerability1'
        },
        {
          reason: '2.) Inyección JS',
          link: '/vulnerability2'
        },
        {
          reason: '3.) Logs Errores Muy Explicitos',
          link: '/vulnerability3'
        },
        {
          reason: '4.) Logs Errroes Muy Explicitos',
          link: '/vulnerability4'
        },
        {
          reason: '5.) Path Errores',
          link: '/vulnerability5'
        },
        {
          reason: '6.) Exposicion Data Sensible (.env)',
          link: '/vulnerability6'
        },
        {
          reason: '7.) Exposicion de ficheros',
          link: '/vulnerability7'
        },
        {
          reason: '8.) Ingresar comando por consola',
          link: '/vulnerability8'
        },
        {
          reason: ' 9. ) Sql Inyeccion',
          link: '/vulnerability9'
        },
        {
          reason: '10.) No-Sql Inyeccion',
          link: '/vulnerability10'
        }
      ]
    }
  }
}
</script>
