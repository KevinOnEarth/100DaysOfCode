<template>
  <v-container>
    <v-row>
     <v-col class="pa-0 ma-0" align="end">
       <v-sheet height="22">
          <v-btn-toggle class="info black--text" active-class="white--text primary" v-model="toggleAmPm">
            <v-btn x-small>On</v-btn>
            <v-btn x-small>Off</v-btn>
          </v-btn-toggle>
       </v-sheet>
     </v-col>
     <v-col class="pa-0 ma-0" cols="12" sm="12">
      <v-sheet height="44">
        <v-toolbar
          dense
          flat
        >
          <v-col align="start">
          <v-btn
            fab
            text
            small
            color="grey darken-2"
            @click="prev"
          >
            <v-icon small>
              mdi-chevron-left
            </v-icon>
          </v-btn>

          </v-col>
          <v-col align="center">
            <v-toolbar-title v-if="$refs.calendar">
              {{ $refs.calendar.title }}
            </v-toolbar-title>
          </v-col>
          <v-col align="end">

          <v-btn
            fab
            text
            small
            color="grey darken-2"
            @click="next"
          >
            <v-icon small>
              mdi-chevron-right
            </v-icon>
          </v-btn>

          </v-col>
        </v-toolbar>
      </v-sheet>
    </v-col>
    <v-col>

      <v-sheet height="400">
        <v-calendar
          ref="calendar"
          :now="today"
          :value="today"
          :weekdays="weekdays"
          :events="events"
          color="primary"
          type="week"
        ></v-calendar>
      </v-sheet>
      </v-col>
    </v-row>
    </v-container>
</template>

<script>
  export default {
    name: 'BareCalendarComponent',
    data: () => ({
      weekdays: [1, 2, 3, 4, 5],
      today: '2021-05-12',
      toggleAmPm: 0,
      events: [
       {
         name: 'Weekly Meeting',
         start: '2021-05-14 09:00',
         end: '2021-05-14 10:00',
       },
       {
         name: `Thomas' Birthday`,
         start: '2021-05-13',
       },
       {
         name: 'Mash Potatoes',
         start: '2021-05-14 12:30',
         end: '2021-05-14 15:30',
       },
       {
         name: 'Sow',
         start: '2021-05-21 12:30',
         end: '2021-05-21 15:30',
       }
      ],
      }),
    mounted () {
      this.$refs.calendar.scrollToTime('08:00')
    },
    methods: {
      prev () {
        console.log('like this?')
        this.$refs.calendar.prev()
      },
      next () {
        console.log('or this?')
        this.$refs.calendar.next()
      },
    }
  }
</script>

<style scoped>
  .my-event {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    border-radius: 2px;
    background-color: #1867c0;
    color: #ffffff;
    border: 1px solid #1867c0;
    font-size: 12px;
    padding: 3px;
    cursor: pointer;
    margin-bottom: 1px;
    left: 4px;
    margin-right: 8px;
    position: relative;
  }

  .my-event.with-time {
    position: absolute;
    right: 4px;
    margin-right: 0px;
  }
</style>
