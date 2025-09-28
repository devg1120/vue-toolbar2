
<script setup lang="ts">
import { ref } from "vue";
import VueSelect from "vue3-select-component";

import { StopIcon  } from './@heroicons/vue/16/solid'
import { PaperAirplaneIcon  } from './@heroicons/vue/24/outline'

const select_color = ref("white");

      //{ label: StopIcon , value: 'silver' },
const options = [
      { label: '' , value: 'white' },
      { label: '' , value: 'silver' },
      { label: '' , value: 'gray' },
      { label: '' , value: 'black' },

      { label: '' , value: 'red' },
      { label: '' , value: 'maroon' },
      { label: '' , value: 'yellow' },
      { label: '' , value: 'olive' },

      { label: '' , value: 'lime' },
      { label: '' , value: 'green' },
      { label: '' , value: 'aqua' },
      { label: '' , value: 'teal' },

      { label: '' , value: 'blue' },
      { label: '' , value: 'navy' },
      { label: '' , value: 'fuchsia' },
      { label: '' , value: 'purple' },
    ];
const options2 = [
      { label: PaperAirplaneIcon, value: 'option_4' },
      { label: PaperAirplaneIcon, value: 'option_4' },
      { label: PaperAirplaneIcon, value: 'option_4' },
    ];

const selected = ref("");


function select(option) {
 console.log("*** selected:", option.value, selected.value)
 select_color.value = option.value;

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

function set_style(color) {
 const style = "background-color:" + color ;
 return style;
}

</script>


<!--
https://vue3-select-component.vercel.app/slots.html
-->

<template>
 <div class="selectitem">
  <VueSelect v-model="selected" :options="options"
    placeholder=""
    @option-selected="select"
    :isClearable="false"
    :isSearchable="false"
  >

    <template #option="{ option, index }"  >
    <!--
	    <div :style="styles[index]" class="item" >&ensp;&ensp;&ensp;</div>
	    -->
	    <div :style="set_style(option.value)" class="item" >&ensp;&ensp;&ensp;</div>
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
:deep(.input-container) {
  background-color: v-bind(select_color);
  /* color: v-bind(select_color); */
  width:16px;
  height:16px;

}
</style>
