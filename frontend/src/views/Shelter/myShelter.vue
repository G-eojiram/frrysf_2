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
    <div>
        <div class="flex justify-between items-center">
            <div class="graycolor">
                <contents msg="My Shelter"/>
            </div>
            <div class="flex gap-5">
                <button class="bg-teal-400 hover:bg-teal-500 flex items-center gap-2 py-[2px] px-[1.5rem] rounded-md">
                    <img :src="writelICON" alt="" class="sm:w-[1.3rem] lg:w-[1.5rem]" />
                    <span class="text-white font-semibold sm:text-[11px] lg:text-[12px]">Edit Profile</span>
                </button>
                <calendarCard />
            </div>
        </div>
    </div>
</template>