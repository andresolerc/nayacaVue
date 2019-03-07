<template>
<div class="container-fluid">
  <div class="row">
    <div class="col-12" id="footer">
      &copy; Nayaca 2019
      &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
      <a href="#">Legal</a>
      &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
      <a href="#">Contact</a>
      &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
      <a href="#"><img src="../assets/media/instagram.png" id="instagram"></a>
      &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
      <a href="#"><img src="../assets/media/usa.png" id="usaflag"></a>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TheFooter',
  components: {
  }
}
</script>

<style>

#footer {
  background-color: black;
  color: white;
  text-align: center;
  font-size: 10px;
  padding: 3px;
  margin: 0;
}

#footer a {
  font-size: 10px;
  color: white;
  text-decoration: none;
}

#instagram {
  filter: invert(100%);
  height: 15px;
}

#usaflag {
  height: 13px;
  border: 1px solid white;
}

</style>
