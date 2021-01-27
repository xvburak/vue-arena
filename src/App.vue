<template>
  <div id="app">
    <arena-images :contents="contents" />
    <bottom />
  </div>
</template>

<script>
  import ArenaImages from '@/components/ArenaImages.vue'
  import Bottom from '@/components/Bottom.vue';
  const Arena = require("are.na");
  const arena = new Arena();
 


  export default {
    name: 'app',
    components: {
      ArenaImages,
      Bottom  
    },
    data(){
      return {
        contents: [ ],
        options: {}
      }
    },
    mounted() {
      this.getEmployees()
    },
    methods: {
        async getEmployees() {
          // arena
          //   .channel("unbranding-agency")
          //   .contents({ page: 1, per: 3 })
          //   .get()
          //   .then(chan => {
          //     console.log(chan.contents);
          //     this.contents = chan.contents;
          //     this.chan = chan;
          //   })
          //   .catch(err => console.log(err));
          arena
            .channel('unbranding-agency')
            .contents({ page: 1, per: 100 })
            .then(contents => {
                console.log(contents);
                this.contents = contents;
                })
            .catch(err => console.log(err));
        },
      },
  }
</script>


<style scoped lang="scss">
</style>