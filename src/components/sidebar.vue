<template>
  <div id="app">
        <sidebar-menu :menu="menu" />
  </div>
</template>

<script>
export default {
  data () {
      
    return {
       menu: [
                {
                    href: '/',
                    title: 'Dashboard',
                    icon: 'fa fa-user'
                },
                {
                    href: '#',
                    title: 'Charts',
                    icon: 'fa fa-chart-area'
                }
            ]
    }
  }
}
</script>

<style lang="scss">
</style>
