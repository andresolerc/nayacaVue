<template>
  <div class="home">
    <div class="jumbotron" id="main">
        <the-navbar/>

  <div class="test" id="message">
    <div id="headline">
      <h4 class="xxs-screen">GET YOUR DREAM JOB</h4>
      <h4 class="xs-screen">GET YOUR DREAM JOB</h4>
      <h3 class="sm-screen">GET YOUR DREAM JOB</h3>
      <h2 class="md-screen">GET YOUR DREAM JOB</h2>
      <h1 class="lg-screen">GET YOUR DREAM JOB</h1>
      <h1 class="xl-screen display-4">GET YOUR DREAM JOB</h1>
      <h1 class="xxl-screen display-3">GET YOUR DREAM JOB</h1>
      <h1 class="xxxl-screen display-2">GET YOUR DREAM JOB</h1>
      <h1 class="xxxxl-screen display-1">GET YOUR DREAM JOB</h1>
    </div>

    <div id="subheads">
      <h6 class="xs-screen sm-screen md-screen lg-screen">CREATE A PERFECT RESUME.</h6>
      <h6 class="xs-screen sm-screen md-screen lg-screen">SHOW YOU'RE THE ONE.</h6>
      <h4 class="xl-screen xxl-screen xxxl-screen xxxxl-screen">CREATE A PERFECT RESUME.</h4>
      <h4 class="xl-screen xxl-screen xxxl-screen xxxxl-screen">SHOW YOU'RE THE ONE.</h4>
    </div>

    <div id="subheadslandscape">
      <h6 class="small-landscape">CREATE A PERFECT RESUME. SHOW YOU'RE THE ONE.</h6>
      <h4 class="large-landscape">CREATE A PERFECT RESUME. SHOW YOU'RE THE ONE.</h4>
    </div>

    <div class="container-fluid" id="gotoresume">
      <div class="row">
        <div class="col">

          <router-link to="/resume"><b-button class="btn btn-pantone btn-sm" role="button" variant="outline-secondary" id="gotoresumebuttonsm">Create Resume</b-button></router-link>
          <router-link to="/resume"><b-button class="btn btn-pantone btn-lg" role="button" variant="outline-secondary" id="gotoresumebuttonlg">Create Resume</b-button></router-link>


        </div>
      </div>
    </div>


  </div>
</div>

<div class="jumbotron" id="ragazza">
  <div class="row">
    <div class="col-6">
    </div>
    <div class="col-6" id="ragazzabox">
      <span>
      <img src="../assets/media/hand-icon.png" alt="Hand icon">
      <h5>EASY</h5>
      <h6>Compose & Edit!</h6>
      <p>Compose your resume in simple steps.<br>
        Edit any time to match new positions.</p>
      <br>
      <img src="../assets/media/rabbit-icon.png" alt="Rabbit icon">
      <h5>FAST</h5>
      <h6>Save precious time!</h6>
      <p>You have a life out there. Get your resume<br>
        in a matter of minutes, not days.</p>
      <br>
      <img src="../assets/media/job-icon.png" alt="Job icon">
      <h5>SUCCESSFUL</h5>
      <h6>Amazing results!</h6>
      <p>Stand out with a design resume.<br>
        Get your dream job, internship, rent...</p>
      </span>
    </div>
  </div>
</div>
      <the-footer/>
</div>
</template>

<script>
    import TheNavbar from '../components/TheNavbar';
    import TheFooter from '../components/TheFooter';

export default {
  name: 'home',
  components: {
      'the-navbar': TheNavbar,
      'the-footer': TheFooter
  }
}

/* window.addEventListener("scroll", function() {
    if (pageYOffset > 200) {
      document.getElementById("message").classList.add('ghost');
    } else {
      document.getElementById("message").classList.remove('ghost');
}
}); */
</script>

<style lang="scss">
  @import '../modules/home.css';

  $pantone: #FF6F61;
  $white: #fff;

  .btn-pantone, #gotoresumebuttonsm, #gotoresumebuttonlg {
    color: $white;
    background-color: $pantone;
    border-color: $white; }

</style>
