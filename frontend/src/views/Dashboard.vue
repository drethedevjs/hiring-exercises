<template>
  <div>
    <!-- This example requires Tailwind CSS v2.0+ -->
    <div>
      <nav class="bg-gray-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex items-center justify-between h-16">
            <div class="flex items-center">
              <div class="flex-shrink-0">
                <img class="h-32 w-32" src="/img/logo.png" alt="Workflow" />
              </div>
              <div class="hidden md:block">
                <div class="ml-10 flex items-baseline space-x-4">
                  <router-link
                    class="text-gray-900 hover:bg-blue-400 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
                    to="dashboard"
                  >
                    Dashboard
                  </router-link>
                  <router-link
                    class="text-gray-900 hover:bg-blue-400 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
                    to="/"
                  >
                    Home
                  </router-link>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Mobile menu, show/hide based on menu state. -->
        <div class="md:hidden" id="mobile-menu">
          <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
            <a href="#" class="bg-gray-900 text-white block px-3 py-2 rounded-md text-base font-medium">Dashboard</a>
            <router-link
              class="text-gray-900 hover:bg-blue-400 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
              to="home"
            >
              Home
            </router-link>
          </div>
        </div>
      </nav>

      <header class="bg-white shadow">
        <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
          <h1 class="text-3xl font-bold text-gray-900">Your Investment</h1>
        </div>
      </header>
      <main>
        <div class="max-w-7xl mx-auto py-6 sm:px-6 lg:px-8">
          <div class="mt-6 px-4 py-6 sm:px-0">
            <headline-stats initialInvestmentCents="initialInvestmentCents" interestRate="interestRate" accountEstablishedDate="accountEstablishedDate" />
            <investment-table class="mt-6" />
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import InvestmentTable from "../components/dashboard/InvestmentTable.vue"
import HeadlineStats from "../components/dashboard/HeadlineStats.vue"
export default {
  name: "Dashboard",
  components: { InvestmentTable, HeadlineStats },
  methods:{
    getAccount: async function()
    {
      // This would not run for some reason. Not sure why.
      // I wanted to get the account information and pass the details
      // as props into the HeadlineStats.vue file

      // await this.$store.dispatch("accounts/getAccount").then(res => {
      //   console.log("Account Information: " + res)
      // },
      // res => 
      // {
      //   console.log("Failed: " + res)
      // })
    },
    getTransactions: async function()
    {
      // Again, I didn't have time to figure out why this wasn't working.
      // I would have passed the response as props into the table component
      // and mapped/looped/repeated the data inserting the values/properties
      // where they needed to go.

      // await this.$store.dispatch("accounts/getAccountTransactions").then(res => {
      //   console.log("Account Transactions: " + res)
      // },
      // res => 
      // {
      //   console.log("Failed: " + res)
      // })
    }
  },
  mounted(){
    this.getAccount();
    this.getTransactions();
  }
}
</script>
