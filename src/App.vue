<script setup>
import{ref,reactive} from 'vue'

const buttons=reactive([
{
  buttonNo:1,
  buttonStatus:'on',
  buttonOnColor: 'bg-blue-500',
  status:1
},
{
  buttonNo:2,
  buttonStatus:'on',
  buttonOnColor: 'bg-blue-500',
  status:1
},
{
  buttonNo:3,
  buttonStatus:'off',
  buttonOnColor: 'bg-gray-500',
  status:0
}
]
  )

  const lights=reactive([
    { 
      lightNo: 1,
      src:"//img.icons8.com/?size=512&id=12244&format=png"
    },

    { 
      lightNo: 2,
      src:"//img.icons8.com/?size=512&id=12244&format=png"
    },

    { 
      lightNo: 3,
      src:"//img.icons8.com/?size=512&id=75&format=png"
    }

  ])
function change(i){
if(buttons[i].status){
  buttons[i].status=!buttons[i].status
   buttons[i].buttonOnColor='bg-gray-500'
   lights[i].src="//img.icons8.com/?size=512&id=75&format=png"
 buttons[i].buttonStatus='off'
}
else if(!buttons[i].status){
  buttons[i].status=!buttons[i].status
   buttons[i].buttonOnColor='bg-blue-500'
   lights[i].src="//img.icons8.com/?size=512&id=12244&format=png"
   buttons[i].buttonStatus='on'
}

}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                
                <button @click="change(index)" v-for="button,index in buttons" :key="buttons.buttonNo" :class="button.buttonOnColor" class="  text-white font-bold py-2 px-4 rounded">
                    Light {{ button.buttonNo  }} {{ button.buttonStatus }}
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
              <img  class="w-20" src="" alt="">
                <img class="w-20" v-for="light in lights" :key="light.lightNo" :src="light.src" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped></style>