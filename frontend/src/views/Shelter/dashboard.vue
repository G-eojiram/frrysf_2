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
      writelICON: require('@/assets/images/write.png'),
      heartPaw: require('@/assets/images/Heartdogpaw.png'),
      //image
      pet: require('@/assets/images/rescue.png'),
      map: require('@/assets/images/mapExample.png'),
      // for loop for updates content
      updateActivity: [
        {
          label: 'Profile Visits',
          value: '00',
          icon: require('@/assets/images/Profile.png'),
          color: 'green',
          width: '4rem'
        },
        {
          label: 'Number of Pets',
          value: '00',
          icon: require('@/assets/images/Animal.png'),
          color: 'teal',
          width: '4rem'
        },
        {
          label: 'Reviews',
          value: '00',
          icon: require('@/assets/images/Ratings.png'),
          color: 'amber',
          width: '2.9rem'
        }
      ],
      // for loop for recent activies
      recentActivities: [
        {
          datetime: "2023-03-01 14:30:00",
          location: "Acacia",
          status: "Successful Dog Rescue"
        },
        {
          datetime: "2023-03-01 13:15:00",
          location: "Panacan",
          status: "Rescued Abandon Cat"
        },
        {
          datetime: "2023-02-28 10:00:00",
          location: "New Ecoland",
          status: "Reported"
        },
        {
          datetime: "2023-02-27 16:45:00",
          location: "Mintal",
          status: "Unknown Report"
        },
        {
          datetime: "2023-02-26 12:30:00",
          location: "Toril",
          status: "Report Responded"
        },
        {
          datetime: "2023-02-25 09:15:00",
          location: "Talomo",
          status: "Reported"
        }
      ]
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

.hover\:bg-lightgreen:hover {
    --tw-bg-opacity: 1;
    background-color: #35c184;
}
</style>

<template>
  <div>
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
          <div v-for="(item, index) in updateActivity"
            :key="index" class="border rounded-lg bg-white drop-shadow-md p-[1rem] sm:w-[9rem] md:w-[13rem] grid place-content-center justify-items-center">
            <span class="font-semibold sm:text-[14px] lg:text-[17px]">{{ item.label }}</span>
            <span :class="`text-${item.color}-500 font-bold lg:text-[30px]`">{{ item.value }}</span>
            <img :src="item.icon" alt="animalshelterdog" :class="`sm:w-[${item.width}] lg:w-[${item.width}]`" />
          </div>
        </div>
      </div>
      <div class="border rounded-lg bg-white drop-shadow-md h-[35rem] sm:mt-[1rem] lg:mt-0 lg:w-[66rem] mx-auto">
        <div class="border rounded-t-md bg-white h-[4rem] flex items-center px-7 gap-x-2">
          <img :src="heartPaw" alt="" class="sm:h-[1.5rem] lg:h-[2rem]" />
          <span class="graycolor font-medium sm:text-[13px] lg:text-[1rem]">Recent Activity</span>
        </div>
        <div class="grid grid-flow-col justify-between h-[31rem]">
          <div class="px-14 py-4 space-y-4 text-[13.5px] overflow-y-auto">
            <div v-for="(item, index) in recentActivities" :key="index" class="grid grid-flow-row">
              <span>{{ item.datetime }}</span>
              <span>{{ item.location }}</span>
              <span>{{ item.status }}</span>
            </div>
          </div>
          <div class="flex justify-center items-center">
            <img :src="map" alt="" class="h-[30.9rem] md:w-[20rem] object-cover" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>