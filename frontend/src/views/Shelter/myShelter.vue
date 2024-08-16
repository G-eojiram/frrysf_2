<script>
import contents from '@/components/message-content.vue'
import calendarCard from '@/components/calendar.vue'
import prolifeCard from '@/components/prolifeCard.vue'
import detailCard from '@/components/detailsCard.vue'
import linkfooter from '@/components/linksFooter.vue'

export default {
  components: {
    contents,
    calendarCard,
    prolifeCard,
    detailCard,
    linkfooter,
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
            <div>
                <calendarCard />
            </div>
        </div>
        <div class="mt-[1rem]">
          <prolifeCard />
        </div>
        <div class="mt-[1rem] flex sm:flex-col md:flex-row lg:flex-row md:justify-between sm:w-full sm:gap-y-[1rem] md:gap-x-[1rem] ">
          <div><detailCard /></div>
          <div class="drop-shadow-md rounded-lg bg-white md:w-[29rem] lg:w-[47rem] h-screen">
            <div class="p-[1rem]">
              <span>feed</span>
            </div>
          </div>
        </div>
        <footer>
          <div>
            <linkfooter/>
          </div>
        </footer>
    </div>
</template>