

<script setup lang="ts">

import { ref , defineEmits, onMounted } from 'vue';
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
import {  Cog6ToothIcon  } from './@heroicons/vue/24/outline'

import { EllipsisVerticalIcon } from './@heroicons/vue/24/outline'
import { EllipsisHorizontalIcon } from './@heroicons/vue/24/outline'
import { DocumentIcon } from './@heroicons/vue/24/outline'

import ToolbarItem6  from './ToolbarItem6.vue'


//import { CalendarIcon } from './@heroicons/vue/16/solid'

//const props = defineProps(['toolbar_define', 'handler_define']);
const props = defineProps(['toolbar_define' ]);

//emit_data = emit_data.concat( props.handler_define );
//emit_data.concat( getHandler() );

const emit = defineEmits(['toolbarItemClick', 'toolbarItemToggle']);
//console.log(emit_data);
//const emit = defineEmits(emit_data);

/*
function getHandler( ) {
    let handlers = [];
    for ( let x = 0; x < props.toolbar_define.length ;x++) {
	 if (props.toolbar_define[x].hasOwnProperty('handler')) {
	     handlers.push(props.toolbar_define[x].handler);
	 }
    }
    return   handlers;
}
function indivisualHandler( name ) {
    for ( let x = 0; x < props.toolbar_define.length ;x++) {
	 if (props.toolbar_define[x].name == name) {
	    //if (props.toolbar_define[x].indhandler) {
	    if (props.toolbar_define[x].handler) {
		 return { result:true, handler:props.toolbar_define[x].handler }
		 //return { result:true, handler:null }
            } else {
	         return  { result:false, handler:null }
	    }
	 }
    }
    return  { result:false, handler:null }
}
*/
function toggle_handler( name , state) {

      emit('toolbarItemToggle', name, state)

}
function click_handler( name ) {
      emit('toolbarItemClick', name)
/*
   let i = indivisualHandler( name ) ;

   //console.log("Click handler :", name, i.result, i.handler);
      
   if (!i.result) {
      emit('toolbarItemClick', name)
   } else {
      emit(i.handler, name)
   }
  */ 
}

onMounted(() => {
 // emit = defineEmits(props.handler_define)
});


</script>

<script lang="ts" >
 //const emit_data= ['toolbarItemClick', 'clickA', 'clickB'];
 let emit_data = ['toolbarItemClick', 'toolbarItemToggle'];
export default {}
</script>

<template>
<div class="toolbar-base">

 <template v-for="item in props.toolbar_define" v-bind:key="item">
	 <ToolbarItem6 v-if="!item.select"  :tooltip="item.tooltip"  :name="item.name" :alignright="item.alignright" 
	                    @toolbarItemClick="click_handler"   
	                    @toolbarItemToggle="toggle_handler"  > 
      <component v-bind:is="item.icon"  class="icon" :class="{ leftspace : item.leftspace, toggle : item.toggle   }"/>
      </ToolbarItem6>
</template>

	</div>
</template>
<style scoped>

.toolbar-base {
  display:flex;
  margin-left: 0px;
  margin-right: 0px;
  padding-left:10px;
  padding-right:10px;
  /* background-color: #f5f5f5;*/
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
/*
.alignright{

  margin-left: auto;

}
*/
</style>
