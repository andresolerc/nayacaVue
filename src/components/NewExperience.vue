<template>
  <li class="experience-box">
    <b-button class="btn btn-sm btn-block" variant="outline-danger" @click="$emit('remove_experience');">Remove experience</b-button>
    <br>
    <input type="text" value="position" class="form-control" placeholder="Position" v-model="position">
    <br>
    <input type="text" value="company" class="form-control" placeholder="Company" v-model="company">
    <br>
    <input type="text" value="location" class="form-control" placeholder="Location" v-model="location">
    <br>
    <input type="text" value="start" class="form-control" placeholder="Start MM.YYYY" v-model="startdate">
    <br>
    <input type="text" value="end" class="form-control" placeholder="End MM.YYYY" v-model="enddate">
    <br>
    <b-button class="btn btn-sm btn-block" :pressed.sync="btnpressed" variant="outline-success" @click="iworkhere">I currently work here</b-button>
    <br>
    <textarea type="text" value="tasks" class="form-control" rows="3" placeholder="My tasks" v-model="tasks"></textarea>
  </li>
</template>

<script>
export default {
  name: 'NewExperience',
  components: {

  }
}
</script>

<style></style>
