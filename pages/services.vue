<template>
  <div class="full-width flex-center flex-column page">
    <div class="full-width page-navigation-container">
      <v-btn flat light :ripple="false">HOME</v-btn>
      <span class="forward-arrow">></span>
      <v-btn flat light :ripple="false">{{ menuItems[index].mainTitle }}</v-btn>
      <span class="forward-arrow">></span>
      <v-btn flat light :ripple="false" color="secondary">{{
        menuItems[index].subtitles[subIndex].title
      }}</v-btn>
      <v-spacer></v-spacer>
    </div>
    <div class="full-width flex-center flex-row page-contents-container">
      <div class="side-section left-section">
        <div class="white--text flex-center top-title">
          <span>SERVICE VALUE</span>
        </div>

        <div class="flex-center flex-column menu-items">
          <v-btn
            class="wrap-button-text"
            flat
            :color="index === itemIndex ? 'blue' : 'white'"
            v-for="(item, itemIndex) of menuItems"
            :key="`service-button-${itemIndex}`"
            @click="index = itemIndex"
            >{{ item.mainTitle }}</v-btn
          >
        </div>
      </div>
      <div class="center-section">
        <div
          class="full-width flex-center flex-row flex-wrap section-navigation-container"
        >
          <v-btn
            class="wrap-button-text"
            :ripple="false"
            flat
            :color="subIndex === index2 ? 'white' : 'black'"
            v-for="(item, index2) of menuItems[index].subtitles"
            :key="`sub-menu-buttons-${index2}`"
            @click="subIndex = index2"
            >{{ item.title }}</v-btn
          >
          <v-spacer></v-spacer>
        </div>
      </div>
      <div class="side-section right-section">
        <div
          class="full-size flex-center flex-column accounting-payroll-container"
        >
          <div
            class="full-width flex-center words-margin-top top-border word-container"
          >
            <span>Accounting & Payroll</span>
          </div>

          <div
            class="full-width flex-center words-margin-top-2 bottom-border word-container"
          >
            <span>Accounting & Payroll</span>
          </div>

          <div class="full-width flex-center flex-column statements">
            <span>Book a call back</span>
            <p class="secondary--text">
              Would you like to discuss your payroll management requirements?
              Fill out the form below:
            </p>
          </div>

          <div class="full-width flex-center flex-column form-container">
            <span>Your Name (required)</span>
            <v-text-field hide-details color="secondary" outline></v-text-field>
            <span>Your Company (required)</span>
            <v-text-field hide-details color="secondary" outline></v-text-field>
            <span>Your Phone Number (required)</span>
            <v-text-field hide-details color="secondary" outline></v-text-field>
            <span>Your Email (required)</span>
            <v-text-field hide-details color="secondary" outline></v-text-field>

            <v-btn depressed color="primary">Submit</v-btn>
          </div>

          <div
            class="full-width flex-center flex-column statements statements-2"
          >
            <span>This payroll management services includes;</span>
            <p class="secondary--text">
              Monthly, weekly or fortnight payroll processing
            </p>
            <p class="secondary--text">PAYE, NSSF & NHIF statutory filings</p>
            <p class="secondary--text">Annual form P9A processing</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Watch } from 'nuxt-property-decorator'

@Component({
  components: {},
})
export default class ServicesPage extends Vue {
  index = 0
  subIndex = 0
  menuItems = [
    {
      mainTitle: 'Accounting & Payroll',
      subtitles: [
        { title: 'Overview' },
        { title: 'Bookkeeping & Financial Accounting' },
        { title: 'Business Process Outsourcing' },
        { title: 'Compilation of Financial Statements' },
        { title: 'Human Resource Consulting' },
        { title: 'Payroll' },
        { title: 'Tax compliance' },
      ],
    },
    {
      mainTitle: 'Tax',
      subtitles: [
        { title: 'Overview' },
        { title: 'Tax Advisory Services' },
        { title: 'Corpoate & Business Tax' },
        { title: 'Payroll' },
        { title: 'Cross Border Tax Advisory' },
      ],
    },
    {
      mainTitle: 'Audit & Assurance',
      subtitles: [
        { title: 'Overview' },
        { title: 'IFRS | statutory Audits' },
        { title: 'Due Diligence' },
        { title: 'Limited Scope Audit' },
        { title: 'IT Assuarance & Analysis' },
      ],
    },
    {
      mainTitle: 'Business Support & Advisory',
      subtitles: [
        { title: 'Overview' },
        { title: 'Finance Department Outsourcing' },
        { title: 'Management Reporting' },
        { title: 'Company Secretarial' },
        { title: 'Information systems' },
      ],
    },
  ]

  @Watch('index')
  mainMenuChange(): void {
    this.subIndex = 0
  }
}
</script>

<style scoped>
.words-margin-top {
  margin-top: 10px;
}

.words-margin-top-2 {
  margin-top: 30px;
}

.word-container {
  height: 30px;

  justify-content: flex-start;

  text-transform: uppercase;

  font-size: 12px;
  font-weight: 500;
}

.top-border {
  border-top: 1px solid #707070;
}

.bottom-border {
  border-bottom: 1px solid #707070;
}

.statements {
  align-items: flex-start;
}

.statements span {
  font-weight: bold;
  margin-bottom: 10px;
}

.statements p {
  font-size: 12px;
}

.statements-1 {
  margin-top: 40px;
}

.statements-2 {
  margin: 20px 0;
}

.statements-2 p {
  margin: 0;
}

.form-container {
  align-items: flex-start;
}

>>> .v-text-field input {
  margin-top: 0;
}

>>> .v-text-field .v-input__slot {
  border-color: #00a9a5 !important;
  min-height: unset;
  border-radius: 0;
}

.form-container .v-btn {
  margin-top: 10px;
  margin-left: 0;
  border-radius: 0;
}
</style>
