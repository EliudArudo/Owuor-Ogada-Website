<template>
  <v-app>
    <!-- 
    
      Navigation drawer placeholder 
    
    -->
    <!-- <v-navigation-drawer
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :to="item.to"
          :key="i"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon" />
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer> -->

    <!-- 

      Toolbar drawer placeholder 

    -->

    <!-- <v-toolbar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-toolbar-side-icon @click="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'" />
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>remove</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"/>
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar> -->

    <div class="full-width flex-center nav-wrapper">
      <div class="full-size flex-center flex-column nav-container">
        <div class="full-width flex-center flex-row top-buttons-container">
          <v-spacer></v-spacer>
          <div class="full-height flex-center flex-row">
            <v-btn color="secondary" depressed>CLIENT LOGIN</v-btn>
            <div class="border">&nbsp;</div>
            <v-btn color="primary" depressed>BOOK CONSULTATION</v-btn>
          </div>
        </div>
        <div
          class="full-width flex-center flex-row flex-wrap contacts-logo-container"
        >
          <div class="flex-center flex-row logo-container">
            <img src="~/assets/img/logo.svg" alt="Logo" />
            <div class="flex-center flex-column logo-info">
              <span class="title">OWUOR OGADA & | ASSOCIATES</span>
              <span class="company">CERTIFIED PUBLIC ACCOUNTANTS</span>
            </div>
          </div>
          <v-spacer></v-spacer>
          <div class="full-height flex-center flex-row nav-contacts">
            <div
              class="full-height accent--text flex-center flex-column contact-words"
            >
              <span>+254 723 946615</span>
              <span>info@oaa.co.ke</span>
              <span>Mon - Sat: 0900 - 2100</span>
            </div>

            <div class="full-height flex-center flex-column contact-icons">
              <img src="~/assets/img/phone-secondary.svg" alt="Phone" />
              <img src="~/assets/img/mail-secondary.svg" alt="Email" />
              <img src="~/assets/img/working-secondary.svg" alt="Work times" />
            </div>
          </div>
        </div>
        <div class="full-width flex-center flex-row nav-links-container">
          <div class="flex-center flex-row nav-links">
            <v-btn
              flat
              v-for="(item, index) of routerItems"
              :key="`top-nav-${index}`"
              :to="item.route"
              :color="$route.path === item.route ? 'blue' : 'secondary'"
              :ripple="false"
              >{{ item.title }}</v-btn
            >
          </div>
          <v-spacer></v-spacer>
          <v-toolbar-side-icon flat color="secondary" />
        </div>
        <div
          class="full-width section-picture-container"
          :class="{ 'larger-picture-container': this.$route.path === '/' }"
          :style="{
            backgroundImage: `url(${require('~/assets/img/sectors-pic.png')})`,
          }"
        >
          &nbsp;
        </div>
      </div>
    </div>

    <div class="full-width flex-center route-container">
      <div class="full-width route-wrapper">
        <nuxt />
      </div>
    </div>

    <!-- 
    
      Navigation drawer placeholder 
    
    -->

    <!-- <v-navigation-drawer
      :right="right"
      v-model="rightDrawer"
      temporary
      fixed
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer> -->
    <v-footer>
      <div class="full-size flex-center footer">
        <div class="full-size footer-container">
          <div
            class="white--text full-width flex-center flex-row flex-wrap top-footer-container"
          >
            <div class="flex-center flex-column first-section-wrapper">
              <img src="~/assets/img/footer-logo.svg" alt="Logo" />
              <span class="secondary--text">OWUOR OGADA & | ASSOCIATES</span>
              <p>
                We are a team of proficient and dedicated professional
                consultants consisting of certified public accountants,
                chartered financial analysts, statisticians and actuaries based
                in Nairobi, Kenya. We typically handle all branches of
                accounting and auditing including accounts outsourcing, business
                taxation, corporate compliance, company formation in Kenya,
                registration of foreign companies, taxation of expatriates etc
              </p>
            </div>

            <div class="flex-center flex-column first-middle-section">
              <div
                class="flex-center flex-row flex-wrap top-first-middle-section"
              >
                <div
                  class="flex-center flex-column nav-section"
                  v-for="(item, index) of footerItems"
                  :key="`nav-section-${index}`"
                >
                  <span class="secondary--text">{{ item.title }}</span>

                  <v-btn
                    :ripple="false"
                    flat
                    small
                    dark
                    v-for="(button, index2) of item.buttons"
                    :key="`nav-section-button-${index}-${index2}`"
                    >{{ button.title }}</v-btn
                  >
                </div>
              </div>

              <div class="flex-center flex-column bottom-first-middle-section">
                <span class="secondary--text"
                  >CERTIFICATION & ACCREDITATION</span
                >

                <div class="flex-center flex-row icons-container">
                  <img src="~/assets/img/icpak.png" alt="ICPAK" />
                  <img
                    src="~/assets/img/institute-of-actuaries.png"
                    alt="ICPAK"
                  />
                </div>
              </div>
            </div>

            <div class="flex-center contact-us-wrapper">
              <div class="flex-center contact-us-button">
                <v-btn flat dark>Contact Us</v-btn>
              </div>
            </div>
          </div>
          <div class="full-width flex-center bottom-footer-container">
            <div
              class="full-width full-height flex-center flex-row bottom-footer-wrapper"
            >
              <v-btn :ripple="false" small flat dark>Privacy & Policy</v-btn>
              <v-btn :ripple="false" small flat dark>Disclaimer</v-btn>
              <v-btn :ripple="false" small flat dark>Media</v-btn>
              <v-btn :ripple="false" small flat dark>Transparency Report</v-btn>
              <v-spacer></v-spacer>
            </div>
          </div>
        </div>
      </div>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component, Watch } from 'nuxt-property-decorator'

@Component({})
export default class DefaultLayout extends Vue {
  routerItems = [
    {
      title: 'Home',
      route: '/',
    },
    {
      title: 'About us',
      route: '/about-us',
    },
    {
      title: 'Services',
      route: '/services',
    },
    {
      title: 'Our Team',
      route: '/our-team',
    },
    {
      title: 'Sectors',
      route: '/sectors',
    },
    {
      title: 'Contacts',
      route: '/contact-us',
    },
  ]

  footerItems = [
    {
      title: 'Advice for my business',
      buttons: [
        { title: 'Audit & assuarance' },
        { title: 'Accounting & payroll' },
        { title: 'Tax' },
        { title: 'Business support & advisory services' },
      ],
    },
    {
      title: 'Advice for me',
      buttons: [
        { title: 'Advice for families' },
        { title: 'Investment advice' },
        { title: 'Personal tax' },
        { title: 'Wealth management' },
      ],
    },
    {
      title: 'Locations',
      buttons: [
        { title: 'Nairobi' },
        { title: 'Mombasa' },
        { title: 'Nakuru' },
        { title: 'Kisumu' },
      ],
    },
    {
      title: 'Careers',
      buttons: [{ title: 'Available positions' }, { title: 'Student careers' }],
    },
  ]

  mounted() {
    console.log(this.$route.path)
  }
}
</script>

<style>
/* My special CSS Helpers */
.full-size {
  height: 100%;
  width: 100%;
}

.full-height {
  height: 100%;
}

.full-width {
  width: 100%;
}

.flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.flex-column {
  flex-direction: column;
}

.flex-row {
  flex-direction: row;
}

.flex-wrap {
  flex-wrap: wrap;
}

.flex-wrap-reverse {
  flex-wrap: wrap-reverse;
}

/* App styles */

.nav-wrapper {
  background: rgba(0, 0, 0, 0.02);
}

.nav-container {
  max-width: 1000px;
  background: rgba(0, 0, 0, 0.02);

  justify-content: flex-start;
}
.top-buttons-container {
  height: 27px;
}

.top-buttons-container .v-btn {
  height: 100%;

  border-radius: 0;
  margin: 0;

  font-size: 10px;
}

.top-buttons-container .border {
  height: 65%;
  width: 2px;
  background: #001524;

  margin: 0 5px;
}

.contacts-logo-container {
  height: 80px;
  background: rgba(0, 0, 0, 0.02);
}

.logo-container {
  height: 40px;
}

.logo-container img {
  height: 100%;
  width: auto;
}

.logo-info {
  padding-left: 10px;
  align-items: flex-start;
}

.logo-info .title {
  font-size: 14px !important;
}

.logo-info .company {
  font-size: 10px;
}

.contact-words,
.contact-icons {
  align-items: flex-end;
}

.nav-contacts {
  height: 70%;
}

.nav-contacts .contact-words {
  font-size: 12px;

  justify-content: space-around;
  padding-right: 10px;
}

.nav-contacts .contact-icons {
  justify-content: space-around;
  align-items: center;
}

.nav-contacts .contact-icons img {
  height: 16px;
}

.nav-links-container {
  height: 40px;
}

.nav-links-container {
  background: #001524;

  margin-top: 7px;
}

.nav-links-container .v-btn {
  margin: 0 7px;
}

.nav-links-container .nav-links .v-btn {
  min-width: 40px;

  margin: 0;
  padding: 0 7px;

  font-size: 12px;
}

.section-picture-container {
  height: 200px;
  background: rgba(0, 0, 0, 0.02);

  margin-top: 7px;
}

.section-picture-container {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.larger-picture-container {
  height: 380px;
}

.route-container {
  align-items: flex-start;
}

.route-wrapper {
  max-width: 1000px;
  min-height: 300px;

  padding-top: 20px;
}

.v-footer {
  height: unset !important;
  min-height: 230px;
}

.footer-container {
  max-width: 1000px;
  background: #001524;
}

.footer-container .top-footer-container {
  min-height: 400px;
  align-items: flex-start;
  justify-content: space-around;

  padding-top: 20px;
}

.footer-container .top-footer-container .first-section-wrapper {
  width: 250px;
}

.footer-container .top-footer-container .first-section-wrapper img {
  height: 80px;
  margin-bottom: 15px;
}

.footer-container .top-footer-container .first-section-wrapper span {
  width: 100%;
  text-align: left;

  margin-bottom: 5px;
}

.footer-container .top-footer-container .first-section-wrapper p {
  font-size: 12px;
}

.footer-container .top-footer-container .first-middle-section {
  align-items: flex-end;
}

.footer-container .top-footer-container .top-footer-wrapper p {
  font-size: 12px;
}

.footer-container .top-footer-container .contact-us-wrapper {
  min-height: 350px;
}

.footer-container .top-footer-container .contact-us-button {
  height: 260px;
  width: 80px;

  border: solid 10px #89043d;
}

.footer-container .top-footer-container .contact-us-button .v-btn {
  height: 60px;
  width: 240px;

  font-size: 25px;
}

.footer-container .top-footer-container .contact-us-button .v-btn span {
  text-transform: uppercase;
  transform: rotate(-90deg);
}

.footer-container
  .top-footer-container
  .contact-us-button
  .v-btn
  .v-btn__content {
  transform: rotate(-90deg);
}

.bottom-first-middle-section {
  align-items: flex-start;

  padding: 10px;
}

.bottom-first-middle-section span {
  width: 230px;
  margin-bottom: 15px;
}

.bottom-first-middle-section .icons-container {
  align-items: flex-start;
}

.bottom-first-middle-section .icons-container img {
  height: 40px;

  margin-right: 10px;
}

.footer-container .bottom-footer-container {
  height: 30px;
}

.footer-container .bottom-footer-container .bottom-footer-wrapper {
  max-width: 90%;
  border-top: solid 2px #89043d;
}

.footer-container .bottom-footer-container .bottom-footer-wrapper .v-btn {
  min-width: 40px;

  margin: 0;
  padding: 0 7px;

  font-size: 10px;
  font-weight: 200;
  text-transform: none;
}

.top-first-middle-section {
  align-items: flex-start;
}

.top-first-middle-section .nav-section {
  align-items: flex-start;
  padding: 10px;
}

.top-first-middle-section .nav-section span {
  font-size: 17px;
  margin-bottom: 10px;
}

.top-first-middle-section .nav-section .v-btn {
  text-transform: none;

  height: 15px;
  min-width: 20px;

  margin: 0;
  padding: 0 7px;
  padding-left: 0;

  font-size: 10px;
}

/* Common page styling */
.page {
  justify-content: flex-start;
}

.page-navigation-container {
  height: 40px;

  margin-bottom: 10px;
  background: rgba(0, 0, 0, 0.03);
}

.page-navigation-container .v-btn {
  min-width: 40px;

  margin: 0;
  padding: 0 7px;

  font-size: 12px;
  font-weight: 200;
}

.page-navigation-container .forward-arrow {
  font-size: 15px;

  color: #b3b3b3;
}

.page-contents-container {
  min-height: 380px;
  align-items: flex-start;
}

.side-section {
  min-height: 200px;
  width: 200px;
  background: rgba(0, 0, 0, 0.02);
}

.left-section .top-title {
  height: 30px;

  font-size: 13px;

  background: #001524;
}

.left-section .menu-items {
  margin-top: 7px;
  background: #001524;

  padding: 3px;
}

.wrap-button-text .v-btn__content {
  width: 100%;
  text-align: left;
  white-space: pre-wrap;

  justify-content: flex-start;
}

.left-section .menu-items .v-btn {
  min-height: 30px;
  width: 100%;
  min-width: 40px;

  margin: 3px 0;
  padding: 0 7px;

  font-size: 12px;
  font-weight: 200;

  border-bottom: solid 1px #3512e8;
}

.right-section {
  min-height: 300px;
  padding: 0 7px;
}

.center-section {
  min-height: 400px;
  width: calc(100% - (2 * 200px));
  padding: 0 7px;
}

.center-section .section-navigation-container {
  min-height: 30px;
  background: #00a9a5;

  padding: 5px 0;

  justify-content: flex-start;
}

.center-section .section-navigation-container .v-btn {
  height: unset;
  min-height: 30px;
  max-width: 120px;
  min-width: 40px;

  margin: 0;
  padding: 0 7px;

  font-size: 10px;
  font-weight: 200;
}

.larger-paired-section {
  width: calc(100% - 100px);
}

.full-section {
  width: 100%;
}
</style>
