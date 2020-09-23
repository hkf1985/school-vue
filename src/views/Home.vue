<template>
  <v-header></v-header>
  <div class="wrap">
    <div class="wrap-left">
      <v-nav></v-nav>
    </div>
    <div class="wrap-right">
      <v-content></v-content>
    </div>
  </div>

</template>

<script lang="ts">
import { Options, Vue} from 'vue-class-component';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import text from "@/filters/filter";

import VHeader from "@/components/header/vHeader.vue";
import vNav from "@/components/nav/vNav.vue";
import vContent from "@/components/content/VContent.vue"

@Options({
  components: {
    VHeader,
    vNav,
    vContent
  },
  props:{
    name:{
      default:"name",
      type:String,
    },
  },
  directives:{

  }
})



export default class Home extends Vue {

  private msg = "msg";
  private list = [1,2,3,4]
  created(){
    console.log(this.msg)
    console.log('created')
  }
  mounted(){
    console.log('mounted')
  }
  beforeCreate(){
    console.log('beforeCreate')
  }
  setText(vaule: string){
    return text(vaule)
  }
  setUp(){
      setTimeout(()=>{
        this.list[2] = 5
        console.log(this.list[2])
      },3000)
  }

}
</script>
<style scoped lang="less">
  .wrap{
    width: 100%;
    height:calc(100% - 44px);
    overflow: hidden;
    display: flex;
    .wrap-left{
      flex-shrink: 0;
      width: 240px;
      background-color: @white;
      box-shadow: 4px 0 4px rgba(0,0,0,.15);
      height: 100%;
    }
  }
</style>
