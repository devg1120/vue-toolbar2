
<script setup lang="ts">
import { ref } from "vue";
import VueSelect from "vue3-select-component";

import { PaperAirplaneIcon  } from './@heroicons/vue/24/outline'

const options = [
      { label: 'Option #1' , value: 'option_1' },
      { label: 'Option #2' , value: 'option_2' },
      { label: 'Option #3' , value: 'option_3' },
      { label: 'Option #4' , value: 'option_4' },
      { label: 'Option #5' , value: 'option_5' },
      { label: 'Option #6' , value: 'option_6' },
      { label: 'Option #7' , value: 'option_7' },
      { label: 'Option #8' , value: 'option_8' },
      { label: 'Option #9' , value: 'option_9' },
      { label: 'Option #10', value: 'option_10' },
      { label: 'Option #11', value: 'option_11' },
      { label: 'Option #12', value: 'option_12' },
      { label: 'Option #13', value: 'option_13' },
      { label: 'Option #14', value: 'option_14' },
      { label: 'Option #15', value: 'option_15' },
      { label: 'Option #16', value: 'option_16' },
    ];
const options2 = [
      { label: PaperAirplaneIcon, value: 'option_4' },
      { label: PaperAirplaneIcon, value: 'option_4' },
      { label: PaperAirplaneIcon, value: 'option_4' },
    ];

const selected = ref("");


function select(option) {
 console.log("*** selected:", option.value, selected.value)

}

const styles = [
 "background-color:white",
 "background-color:silver",
 "background-color:gray",
 "background-color:black",

 "background-color:red",
 "background-color:maroon",
 "background-color:yellow",
 "background-color:olive",

 "background-color:lime",
 "background-color:green",
 "background-color:aqua",
 "background-color:teal",

 "background-color:blue",
 "background-color:navy",
 "background-color:fuchsia",
 "background-color:purple",
 ]


</script>


<!--
https://vue3-select-component.vercel.app/slots.html
-->

<template>
 <div class="selectitem">
  <VueSelect v-model="selected" :options="options"
    placeholder="Select2"
    @option-selected="select"
  >
    <template #option="{ option, index }"  >
	    <div :style="styles[index]" class="item" >&ensp;&ensp;&ensp;</div>
    </template>
  </VueSelect>
 </div>
</template>


<style scoped>
/*
:deep(.item) {
   width:160px !important;
}
*/
:deep(.menu) {
  display: grid;
/*
  width: 150px !important;
  grid-template-columns: repeat(auto-fill, minmax(30px, 1fr));

  width: 170px !important;
  grid-template-columns: repeat(auto-fill, minmax(35px, 1fr));
*/
  width: 180px !important;
  grid-template-columns: repeat(auto-fill, minmax(37px, 1fr));
}

</style>
