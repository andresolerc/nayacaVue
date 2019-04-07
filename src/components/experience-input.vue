<template>
  <li class="experience-box">
    <b-button class="btn btn-sm btn-block" variant="outline-danger" @click="$emit('remove_experience');">Remove experience</b-button>
    <br>
    <input type="text" value="position" class="form-control" placeholder="Position" v-model="experience.position">
    <br>
    <input type="text" value="company" class="form-control" placeholder="Company" v-model="experience.company">
    <br>
    <input type="text" value="location" class="form-control" placeholder="Location" v-model="experience.location">
    <br>
    <input type="date" value="start" class="form-control" placeholder="Start MM.YYYY" v-model="experience.startdate">
    <br>
    <input type="date" value="end" class="form-control" placeholder="End MM.YYYY" v-model="experience.enddate">
    <br>
    <b-button class="btn btn-sm btn-block" :pressed.sync="btnpressed" variant="outline-success" v-on:click="iworkhere" v-bind:value="experience.noend">I currently work here</b-button>
    <br>
    <textarea type="text" value="tasks" class="form-control" rows="3" placeholder="My tasks" v-model="experience.tasks"></textarea>
  </li>
</template>

<script>
export default {
  name: 'ExpIn',
  props: ['experience'],
  components: {

  },
  data() {
    return {
      btnpressed: false,
    }
  },
  methods: {
    iworkhere(){
      this.experience.noend = !this.experience.noend;
    }

  },
  computed: {

  },
}
</script>

<style></style>
