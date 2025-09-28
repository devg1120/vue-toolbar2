<script setup lang="ts">

import { ref , defineEmits} from 'vue';
//import VueDatePicker from '@vuepic/vue-datepicker';
//import '@vuepic/vue-datepicker/dist/main.css'
import { CalendarIcon } from './@heroicons/vue/24/outline'
import { TrashIcon } from './@heroicons/vue/24/outline'
import { XMarkIcon } from './@heroicons/vue/24/outline'
import { Square2StackIcon } from './@heroicons/vue/24/outline'
import { RectangleGroupIcon  } from './@heroicons/vue/24/outline'
import { PlusIcon  } from './@heroicons/vue/24/outline'
import { MinusIcon  } from './@heroicons/vue/24/outline'
import { PencilSquareIcon  } from './@heroicons/vue/24/outline'
import { PaperAirplaneIcon  } from './@heroicons/vue/24/outline'
import { PaperClipIcon  } from './@heroicons/vue/24/outline'
import { ArrowPathIcon  } from './@heroicons/vue/24/outline'
import { ArrowUturnRightIcon  } from './@heroicons/vue/24/outline'
import { ArrowUturnLeftIcon  } from './@heroicons/vue/24/outline'
import { ArrowsPointingOutIcon  } from './@heroicons/vue/24/outline'
import { ArrowsPointingInIcon  } from './@heroicons/vue/24/outline'
import { Cog6ToothIcon  } from './@heroicons/vue/24/outline'

import { EllipsisVerticalIcon } from './@heroicons/vue/24/outline'
import { EllipsisHorizontalIcon } from './@heroicons/vue/24/outline'
import { DocumentIcon } from './@heroicons/vue/24/outline'

import ToolbarItem4  from './ToolbarItem4.vue'


//import { CalendarIcon } from './@heroicons/vue/16/solid'

const props = defineProps(['toolbar_define']);

const emit = defineEmits(['toolbarItemClick']);

/*

function clickA( data ) {

   console.log("Click A:", data);
   alert("Click A");
}

function clickB( data ) {

   console.log("Click B:", data);
   alert("Click B");
}
*/

function handler( data ) {

   console.log("Click handler :", data);
   emit('toolbarItemClick', data)
}

/*
const toolbar_define = [

{ icon : ArrowUturnRightIcon,
  name : "ArrowUturnRightIcon",
  handler : clickA,
  tooltip : "A         OK",
},
{ icon : ArrowUturnLeftIcon,
  name : "ArrowUturnLeftIcon",
  handler : clickB,
  tooltip : "B         OK",
},

];
*/

</script>

<template>
<div class="toolbar-base">
	<!--
 <ToolbarItem tooltip="AAAAAAAAAAA111111111111111111 222222222222" @toolbarItemClick="clickA"> <ArrowUturnRightIcon class="icon" /> </ToolbarItem>
 <ToolbarItem tooltip="BBBBBBBBBBB"                       @toolbarItemClick="clickB"> <ArrowUturnLeftIcon class="icon" />  </ToolbarItem>

 <ToolbarItem  tooltip="C AAAAAAAAAA"> <RectangleGroupIcon class="icon" />  </ToolbarItem> 
 <ToolbarItem  tooltip="D AAAAAAAAAA"> <Square2StackIcon class="icon" />    </ToolbarItem>
 <ToolbarItem  tooltip="E AAAAAAAAAA"> <CalendarIcon class="icon leftspace" /> </ToolbarItem>
 <ToolbarItem  tooltip="F AAAAAAAAAA"> <TrashIcon class="icon" />  </ToolbarItem>
 <ToolbarItem  tooltip="G AAAAAAAAAA"> <XMarkIcon class="icon" />  </ToolbarItem>
 <ToolbarItem  tooltip="H AAAAAAAAAA"> <PlusIcon class="icon" />  </ToolbarItem>
 <ToolbarItem  tooltip="I AAAAAAAAAA"> <MinusIcon class="icon" />  </ToolbarItem>
 <ToolbarItem  tooltip="J DYN"> 
	<component v-bind:is="RectangleGroupIcon"  class="icon" />
 </ToolbarItem>
	-->

<!--
 <template v-for="item in props.toolbar_define" v-bind:key="item">
      <ToolbarItem2  :tooltip="item.tooltip"  :name="item.name" @toolbarItemClick="handler"> 
      <component v-bind:is="item.icon"  class="icon" />
      </ToolbarItem2>
</template>
-->

 <template v-for="item in props.toolbar_define" v-bind:key="item">
      <ToolbarItem4  :tooltip="item.tooltip"  :name="item.name" @toolbarItemClick="handler"> 
      <component v-bind:is="item.icon"  class="icon" :class="{leftspace : item.leftspace, toggle : item.toggle  }"/>
      </ToolbarItem4>
</template>
<!--
 <template v-for="item in props.toolbar_define" v-bind:key="item">
      <ToolbarItem4  :tooltip="item.tooltip"  :name="item.name" @toolbarItemClick="handler"> 
      <div v-if="item.leftspace">
         <component v-bind:is="item.icon"  class="icon leftspace" />
      </div>
      <div v-else>
         <component v-bind:is="item.icon"  class="icon" />
      </div>

      </ToolbarItem4>
</template>
-->

<!--
  <RectangleGroupIcon class="icon" />
  <Square2StackIcon class="icon" />
  <CalendarIcon class="icon leftspace" />
  <TrashIcon class="icon" />
  <XMarkIcon class="icon" />
  <PlusIcon class="icon" />
  <MinusIcon class="icon" />
  <PencilSquareIcon class="icon leftspace" />
  <PaperAirplaneIcon class="icon" />
  <PaperClipIcon class="icon" />
  <ArrowsPointingOutIcon class="icon" />
  <ArrowsPointingInIcon class="icon" />
  <ArrowPathIcon class="icon" />
  <Cog6ToothIcon class="icon" />
  <EllipsisVerticalIcon class="icon" />
  <EllipsisHorizontalIcon class="icon" />
  <DocumentIcon class="icon" />
-->
	</div>
</template>
<style scoped>

.toolbar-base {
  display:flex;

}

.icon {
 width : 22px;
 height : 22px;
 cursor: pointer;
 margin: 3px 2px;
 padding: 3px 4px;
 box-shadow: 2px 2px 0px 0 lightgray;

}
 
.icon.mouse-down{
 box-shadow: -2px -2px 0px 0px lightgray;
}

.leftspace {
 margin-left: 20px;

}

</style>
