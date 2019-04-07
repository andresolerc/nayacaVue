<template>
  <li class="exp-out-box">

      <div class="position">
        <h6>{{ experience.position }}</h6>
      </div>

      <div>
        <span class="inliner">
          <img src="../assets/media/icons/company_black.png" height="19px" v-if="experience.company">
          <h6>&nbsp;{{ experience.company }}</h6>
        </span>
      </div>

      <div>
        <span class="inliner">
          <img src="../assets/media/icons/location_black.png" height="19px" v-if="experience.location">
          <h6>&nbsp;{{ experience.location }}</h6>
        </span>
      </div>

      <div>
        <span class="inliner">
          <img src="../assets/media/icons/calendar_black.png" height="19px" v-if="experience.startdate || experience.enddate || experience.noend">
          <h6>&nbsp;{{ period }}</h6>
        </span>
      </div>

      <div>
        <span class="inliner">
          <img src="../assets/media/icons/tasks_black.png" height="19px" v-if="experience.tasks">
          <h6>&nbsp;{{ experience.tasks }}</h6>
        </span>
      </div>

  </li>
</template>

<script>


export default {
  name: 'ExpOut',
  props: ['experience'],
  components: {

  },
  data() {
    return {

    }
  },
  computed: {
    period() { //Belongs to Date period for Experience-Input
      if (this.experience.startdate && this.experience.enddate && this.experience.noend) {
        return 'since ' + this.experience.startdate;
      } else if (this.experience.startdate && this.experience.enddate) {
        return this.experience.startdate + ' - ' + this.experience.enddate;
      } else if (this.experience.startdate && this.experience.noend) {
        return 'since ' + this.experience.startdate;
      } else if (this.experience.enddate && this.experience.noend) {
        return null;
      } else if (this.experience.startdate) {
        return 'since ' + this.experience.startdate;
      } else if (this.experience.enddate) {
        return 'until ' + this.experience.enddate;
      } else if (!this.experience.noend) {
        return 'I currently work here.';
      } else {
        return null;
      }
    },

  }

}

</script>

<style></style>
