<template>
  <div class="blog">
    <div class="jumbotron" id="blog">
        <the-navbar/>

    <div class="headline" id="blogheadline">
      <h1>
        NAYACA'S BLOG
      </h1>
    </div>
    <div class="subheads" id="blogsubheads">
      <h4>
        PERIODIC NOTES ON HOW TO GET YOUR DREAM JOB
      </h4>
    </div>

          <div class="container">
            <div class="row">
              <div class="col-sm latestblogbox">
                <div class="flex-item"><h6>BLOG ENTRY #2</h6><h6>25 December 2018</h6></div>

                <h4>
                  One or more pages for your resume?
                </h4>
                <p>
                  You never get a second chance to make a first impression. This
                  holds true for all sorts of situations you encounter, e.g. meeting
                  that special someone. Think back to the very first impression
                  you’ve ever made: You had just seen the light of day and met a
                  really special person: your mother. How did you handle? You screamed
                  as loud as you could into her face. How did she react? She happily
                  smiled back at you. You can hardly blow it more than you did back
                  then. And you can hardly reap sweeter fruits than you did back
                  then. But here comes the dirty truth: those days are gone for
                  good. So don’t expect to scream into somebody’s face and get
                  anything in return. That’s not going to happen any more. Today
                  you have to be nice to people to get what you want. There’s this
                  amazing guy you really like? Show him he’s amazing, flatter him.
                  There’s this special girl you can’t get your eyes off? Kill her
                  with kindness. Patiently. If she’s a human she’ll get soft. Sooner
                  or later. That being said, making a great first impression always
                  helps.
                  When it comes to the first impression you make regarding your
                  dream job, that is generally your resume. You might think you
                  apply for a position at a company. Well, you do. Most of the time,
                  however, your resume will end up in the hands of the person in
                  charge of hiring you, i.e. a human. You think your skills speak
                  for themselves? Well… no. That is, unless you’re Albert Einstein.
                  Your skillset does matter though. But only to the extent that
                  you have to show you could be a match for the position in question.
                  Usually your most outstanding achievements in the field get this
                  job done. Depending on the person who gets you’re your resume between
                  her fingers, you have approximately 30 seconds to pique her interest
                  to meet you in person, i.e. invite you for a job interview. That’s all
                  you’re trying to achieve by means of your resume – you’re actually
                  applying for a job interview, not a job (yet).
                  This is why one page for your resume usually suffices. That’s all
                  the space you need to list your greatest educational and professional
                  achievements. It also shows that you are a person who gets to the
                  point and respect your counterpart’s time constraints - a key
                  qualification for many jobs. There are exceptions to that general
                  rule, e.g. if you’re applying to be a rocket scientist at NASA.
                  You’re not? Then keep that pottery club in high school to yourself
                  and make the best use of one page to impress the person at the
                  HR department in 30 seconds. And who knows? Maybe you really meet
                  that special someone on the day of your job interview…

                </p>
                <button type="button" class="btn btn-danger btn-sm" href="#">Read more</button>
              </div>
              </div>
              </div>

  </div>

  <div class="container">
        <div class="row">
          <div class="col-sm blogbox">
            <div class="flex-item"><h6>BLOG ENTRY #1</h6><h6>15 December 2018</h6></div>

            <h4>
              A better job away from home?
            </h4>
            <p>
              Bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              Bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla
              bla bla bla bla bla
            </p>
            <button type="button" class="btn btn-danger btn-sm" href="#">Read more</button>
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
  name: 'blog',
  components: {
    'the-navbar': TheNavbar,
    'the-footer': TheFooter
  }
}
</script>

<style lang="scss">
  @import '../modules/blog.css';
</style>
