 <template>
   <div class="progress">
     <div class="progress-bar bg-info" role="progressbar" v-bind:style="{width: progress +'%'}"aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
       {{currentItem }}/10
     </div>
   </div>
 </template>
 <script>
 import {eventBus} from'../../main'
 export default{
   data:function(){
     return {
       currentItem:0,
       progress:0
     }
   },
   created() {
     eventBus.$on("progreesUpdate", (productList) =>{
         this.currentItem=productList;
         this.progress=productList*10;
     });
   }
 }
 </script>