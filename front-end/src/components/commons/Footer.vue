<template>
  <v-footer
    fixed
    height="auto">

    <v-card
      class="flex footer-background-color"
      flat
      tile>

      <v-card-actions class="white justify-space-between">
        <strong>
          &copy;Portfolio 
          <v-btn
            class="mx-3"
            href="https://lab.ssafy.com/cjsong/webmobile-sub2/"
            icon>
          <v-icon size="24px">fa-gitlab</v-icon>
        </v-btn>
        </strong>
        <WeatherParse></WeatherParse>
      </v-card-actions>
    </v-card>
  </v-footer>
</template>


<script>
import WeatherParse from '../commons/WeatherParse'

export default {
  name: 'Footer',

  components : {
    WeatherParse,
  },

  data: () => ({
    icons: [

    ]
  })
}
</script>
