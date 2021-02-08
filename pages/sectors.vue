<template>
  <div class="full-width flex-center flex-column page">
    <div class="flex-center flex-row full-width page-navigation-container">
      <v-btn flat light :ripple="false">HOME</v-btn>
      <span class="forward-arrow">></span>
      <v-btn flat light :ripple="false">ACCOUNTING & PAYROLL</v-btn>
      <span class="forward-arrow">></span>
      <v-btn flat light :ripple="false" color="secondary">{{
        menuItems[menuIndex].title
      }}</v-btn>
      <v-spacer></v-spacer>
    </div>

    <div class="full-width flex-center flex-row page-contents-container">
      <div class="side-section left-section">
        <div class="white--text flex-center top-title">
          <span>SECTORS</span>
        </div>

        <div class="flex-center flex-column menu-items">
          <v-btn
            class="wrap-button-text"
            flat
            v-for="(item, index2) of menuItems"
            :color="menuIndex === index2 ? 'blue' : 'secondary'"
            :key="`menu-item-${index2}`"
            @click="menuIndex = index2"
            >{{ item.title }}</v-btn
          >
        </div>
      </div>
      <div class="center-section">
        <div
          class="full-width flex-center flex-row flex-wrap section-navigation-container"
        >
          &nbsp;
        </div>
      </div>
      <div class="side-section right-section">
        <div class="full-size flex-center flex-column right-section-container">
          <div class="full-width flex-center flex-column statements-container">
            <span class="secondary--text work-title">{{
              users[index].title
            }}</span>
            <span class="accent--text work-name">{{ users[index].name }}</span>

            <div class="full-width flex-center flex-row contact-item">
              <img src="~/assets/img/phone-secondary.svg" alt="Phone" />
              <span>{{ users[index].phone }}</span>
            </div>

            <div class="full-width flex-center flex-row contact-item">
              <img src="~/assets/img/mail-secondary.svg" alt="Phone" />
              <span>{{ users[index].email }}</span>
            </div>
          </div>

          <div class="full-width flex-center work-image-container">
            <img :src="users[index].image" alt="Image" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({
  components: {},
})
export default class SectorsPage extends Vue {
  menuIndex = 0
  index = 0
  users = [
    {
      title: 'PARTNER - HEAD OF ASSURANCE',
      name: 'PHIDELIS WAIRIMU NDUTA',
      phone: '+254 20 6750915',
      email: 'ndutap@ooa.co.ke',
      image: require('~/assets/img/work-image.png'),
    },
  ]

  menuItems = [
    {
      title: 'Manufacturing',
    },
    {
      title: 'Retirement Benefits Scheme',
    },
    {
      title: 'Hospitality',
    },
    {
      title: 'Agribusiness',
    },
    {
      title: 'Retail',
    },
    {
      title: 'Charter Schools',
    },
    {
      title: 'Professionals',
    },
    {
      title: 'Financial Services',
    },
  ]
}
</script>


<style scoped>
.right-section {
  padding: 0;
}

.statements-container {
  align-items: flex-start;
  padding: 10px;
}

.contact-item {
  height: 30px;
  justify-content: flex-start;
}

.contact-item span {
  margin-left: 5px;
}

.work-title {
  font-size: 11px;
  margin-bottom: 10px;
}

.work-name {
  margin-bottom: 15px;
}

.work-image-container {
  margin-bottom: 30px;
}

.work-image-container img {
  width: 100%;
}
</style>