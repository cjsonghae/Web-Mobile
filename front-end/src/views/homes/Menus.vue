<template>
  <div>
    <v-layout class="mt-3">
      <v-flex>
        <router-link to="/aboutus" :class="{'red-color': aboutUsPicked}" class="menu-title">
          <div @mouseleave="aboutUsPick" @mouseover="aboutUsPick">
            About Us
          </div>
        </router-link>

        <router-link to="/posts" :class="{'red-color': postsPicked}" class="menu-title">
          <div @mouseleave="postsPick" @mouseover="postsPick">
            Posts
          </div>
        </router-link>

        <router-link to="/portfolios" :class="{'red-color': portfoliosPicked}" class="menu-title">
          <div @mouseleave="portfoliosPick" @mouseover="portfoliosPick">
            Portfolios
          </div>
        </router-link>

      </v-flex>
    </v-layout>

    <div v-if="isLoggedIn">
      <v-layout class="mt-3 ml-2">
      <Logout></Logout>
      </v-layout>
    </div>

    <div v-else>
      <v-layout class="mt-3 ml-2">
      <LoginModal></LoginModal>
      <SignupModal></SignupModal>
      </v-layout>
    </div>
  
  </div>
</template>


<script>
/**
 * 각 페이지로 이동하는 Menu를 출력하는 component
 * Login과 Signup은 Modal을 사용하기 때문에 따로 component로 분리
 */

import LoginModal from '../../components/accounts/LoginModal'
import SignupModal from '../../components/accounts/SignupModal'
import Logout from '../../components/accounts/Logout'

export default {
  name: "Menus",

  components: {
    LoginModal,
    SignupModal,
    Logout,
  },

  methods: {
    postsPick() { this.postsPicked = !this.postsPicked },
    portfoliosPick() { this.portfoliosPicked = !this.portfoliosPicked },
    aboutUsPick() { this.aboutUsPicked = !this.aboutUsPicked },
    signupPick() { this.signupPicked = !this.signupPicked },
  },

  data() {
    return {
      postsPicked: false,
      portfoliosPicked: false,
      aboutUsPicked: false,
      signupPicked: false,
    }
  },

  computed: {
    isLoggedIn () {
      return this.$store.state.isLoggedIn;
    }
  }
}
</script>

<style>
.text {
  display: inline-block!important;
}
</style>
