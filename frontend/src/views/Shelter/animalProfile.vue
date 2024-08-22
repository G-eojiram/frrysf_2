<script>
import { PencilIcon } from '@heroicons/vue/20/solid'
import contents from '@/components/message-content.vue'
import calendarCard from '@/components/calendar.vue'
import linkfooter from '@/components/linksFooter.vue'

export default {
  components: {
    contents,
    calendarCard,
    linkfooter,
    PencilIcon,
  },
  data() {
    return {
    //icons
      pending: require('@/assets/images/Data Pending.png'),
      users: require('@/assets/images/People.png'),
      complaints: require('@/assets/images/Strike.png'),
      calendarICON: require('@/assets/images/Calendar.png'),

      profiles: [
        {
            name: 'Eric',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'Bals',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'Chellsey',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'Cyril',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'Jeneh',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'blink-blink',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'heinz',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
        {
            name: 'Jeneh',
            petType: 'Bulldog',
            imageUrl:
                require('@/assets/images/animalshelterdog.png'),
        },
    ]
    }
  },
}
</script>
<template>
    <div>
        <div class="flex justify-between items-center">
            <div class="graycolor">
                <contents msg="Animal Profile"/>
            </div>
            <div class="flex gap-3 sm:gap-1 items-center">
                <div class="bgorange py-[.40rem] px-[1rem] sm:px-[12px] rounded-md hover:bg-bgdarkorange">
                    <router-link to="/createAnimalProfileform" class="flex gap-x-1">
                        <PencilIcon class="-ml-0.5 mr-1.5 sm:h-4 sm:w-4 md:h-5 md:w-5 text-white" aria-hidden="true" />
                        <span class="text-white font-medium text-[13.5px] sm:text-[11.6px]">Create New Profile</span>
                    </router-link>
                </div>
                <div class="sm:px-[1px]">
                    <calendarCard />
                </div>
            </div>
        </div>
        <div class="mt-[1rem]">
            <ul id="profile-columns" role="list" class="grid grid-cols-1 gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
                <li v-for="pets in profiles" :key="pets.name"
                    class="col-span-1 flex flex-col divide-y divide-gray-200 rounded-lg bg-white text-center drop-shadow-md">
                    <div class="flex flex-1 flex-col p-7">
                        <img class="mx-auto w-52 h-52 flex-shrink-0" :src="pets.imageUrl" alt="" />
                        <h3 class="mt-6 text-sm font-medium text-gray-900">{{ pets.name }}</h3>
                        <dl class="mt-1 flex flex-grow flex-col justify-between">
                            <dt class="sr-only">Aninal Type</dt>
                            <dd class="text-sm text-gray-500">{{ pets.petType }}</dd>
                        </dl>
                    </div>
                    <div>
                        <div class="text-[14px] bg-slate-50 p-[1rem] hover:bg-bgteal hover:text-white rounded-b-lg">
                            <router-link to="/viewprofileform">
                                <span class="px-[5rem] py-[1rem]">View Profile</span>
                            </router-link>
                        </div>
                    </div>
                </li>
            </ul>
        </div>
        <footer>
          <div>
            <linkfooter/>
          </div>
        </footer>
    </div>
</template>