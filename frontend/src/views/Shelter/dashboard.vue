<script>
import contents from '@/components/message-content.vue'
import calendarCard from '@/components/calendar.vue'

export default {
  components: {
    contents,
    calendarCard
  },
  data() {
    return {
      //icons
      pending: require('@/assets/images/Data Pending.png'),
      users: require('@/assets/images/People.png'),
      complaints: require('@/assets/images/Strike.png'),
      calendarICON: require('@/assets/images/Calendar.png'),
      profileICON: require('@/assets/images/Profile.png'),
      ratingICON: require('@/assets/images/Ratings.png'),
      animalICON: require('@/assets/images/Animal.png'),
      writelICON: require('@/assets/images/write.png'),
      //image
      pet: require('@/assets/images/rescue.png'),
    }
  },
}
</script>

<style>
.lightgraycolor{
    background: #F5F5F5;
}
.graycolor{
    color: #5A5A5A;
}
.lightgreen{
  background-color: #40d494;
}
</style>

<template>
    <div class="flex justify-between items-center">
        <div class="graycolor">
            <contents msg="Dashboard"/>
        </div>
        <div class="flex gap-5">
          <button class="lightgreen flex items-center gap-2 py-[2px] px-[1.5rem] rounded-md">
            <img :src="writelICON" alt="" class="w-[1.5rem]" />
            <span class="text-white font-semibold text-[12px]">New Post</span>
          </button>
            <calendarCard />
        </div>
    </div>

    <div class="mt-[1rem] lg:flex lg:gap-7">
      <div>
        <div>
          <img :src="pet" alt="animalshelterdog" class="lg:h-[23.5rem] lg:w-screen"/>
        </div>
        <div class="grid grid-flow-col sm:space-x-4 md:space-x-6 place-content-center justify-items-center sm:mt-[1rem]">
          <div class="border rounded-lg bg-white drop-shadow-md p-[1rem] sm:w-[9rem] md:w-[13rem] grid place-content-center justify-items-center">
            <span class="font-semibold sm:text-[14px] lg:text-[17px]">Profile Visits</span>
            <span class=" text-green-500 font-bold lg:text-[30px]">00</span>
            <img :src="profileICON" alt="animalshelterdog" class="sm:w-[4rem] lg:w-[5rem]"/>
          </div>
          <div class="border rounded-lg bg-white drop-shadow-md p-[1rem] sm:w-[9rem] md:w-[13rem] grid place-content-center justify-items-center">
            <span class="font-semibold sm:text-[13.3px] lg:text-[17px]">Number of Pets</span>
            <span class=" text-green-500 font-bold lg:text-[30px]">00</span>
            <img :src="animalICON" alt="animalshelterdog" class="sm:w-[4rem] lg:w-[5rem]"/> 
          </div>
          <div class="border rounded-lg bg-white drop-shadow-md p-[1rem] sm:w-[9rem] md:w-[13rem] grid place-content-center justify-items-center">
            <span class="font-semibold sm:text-[14px] lg:text-[17px]">Reviews</span>
            <span class=" text-green-500 font-bold lg:text-[30px]">00</span>
            <img :src="ratingICON" alt="animalshelterdog" class="sm:w-[2.9rem] lg:w-[3.5rem]"/>
          </div>
        </div>
        <!-- <div class="border rounded-lg bg-white drop-shadow-md h-[20rem] mt-[1rem] py-[2rem] px-[4rem]">
          <div class="mb-[1rem]">
            <span class="font-bold graycolor lg:text-[17px]">Name sa Shelter</span>
          </div>
          <input type="text" id="email" placeholder="What's on your mind..."
            class="border rounded-lg py-2 px-[2rem] w-[33rem]">
        </div> -->
      </div>
      <div class="border rounded-lg bg-white drop-shadow-md h-[35rem] sm:mt-[1rem] lg:mt-0 lg:w-screen">
        <div class="border rounded-t-md bg-white h-[4rem]">

        </div>
        <div>
        </div>
      </div>
    </div>


    <!-- <div class="my-[1rem] lg:flex lg:gap-x-[2rem]">
      <div>
        <div class="relative">
          <img :src="pet" alt="animalshelterdog" class=""/>
          <div class="lg:absolute lg:top-[13rem] lg:left-0 w-full h-full lg:flex justify-center items-center lg:z-10">
            <div class="flex gap-x-[2rem]">
              <div class="border rounded-md bg-white w-[12rem] p-[2rem]">
                <div class="grid place-content-center justify-items-center">
                  <span>Profile Visits</span>
                  <span>Reviews</span>
                  <img :src="profileICON" alt="animalshelterdog" class="w-[5rem]"/>
                </div>
              </div>
              <div class="border rounded-md bg-white w-[12rem] p-[2rem]">
                <div class="grid place-content-center justify-items-center">
                  <span>Number of Pets</span>
                  <span>Reviews</span>
                  <img :src="animalICON" alt="animalshelterdog" class="w-[5rem]"/>                 
                </div>
              </div>
              <div class="border rounded-md bg-white w-[12rem] p-[2rem]">
                <div class="grid place-content-center justify-items-center">
                  <span>Reviews</span>
                  <span>Reviews</span>
                  <img :src="ratingICON" alt="animalshelterdog" class="w-[3.5rem]"/>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-[7rem] border rounded-lg bg-white drop-shadow-md h-[17.4rem]">
          dsad
        </div>
      </div>
      <div class="border rounded-md bg-white drop-shadow-md lg:w-[90rem] h-[50rem]">
        <div class="border rounded-t-md bg-white h-[4rem]">
        </div>
        <div class="p-[1rem]">
          dsad
        </div>
      </div>
    </div> -->
</template>