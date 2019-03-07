<template>
  <div class="resume">
      <div class="container-fluid" id="resumeheader">
            <div class="row">
                <div class="col-6" id="brandcol">

                    <router-link to="/" class="navbar-brand">
                      <img src="../assets/media/nayaca-white-logo.png" alt="Nayaca" id="brandimage">
                    </router-link>
                </div>
                <div class="col-6" id="SignUpCol">
                      <b-button type="button" class="btn" size="sm" id="signupbutton" href="#"><span>Sign Up</span></b-button>
                </div>
                <div class="col-12" id="progresscol">
                      <b-progress class="mb-3"  animated min-width id="progress" >
                                <!-- Want to display progress number? add:  show-progress :label="valuebar + '%'" -->
                                <b-progress-bar :max="maxbar" :value="valuebar"  id="progressive"/>
                      </b-progress>
                </div>
            </div>
      </div>

      <div class="container" id="resumebuilder">
          <div class="row">
              <div class="col-md-4">
                  <b-form class="resumeform">
                        <b-form-group id="about_box">
                              <b-button href="#" v-b-toggle.accordion1 class="btn btn-sm btn-block" variant="outline-dark" id="btnabout">ABOUT</b-button>
                              <b-collapse id="accordion1" accordion="my-accordion" role="tabpanel"><br>
                              <b-form-input type="text" id="name" placeholder="My name" v-model="full_name" class="onProgressbar" @focus="checkCompleted" ></b-form-input><br>
                              <b-form-input type="text" id="current_position" placeholder="My current position" v-model="current_position" ></b-form-input><br>
                              <b-form-input type="text" id="current_company" placeholder="My current company" v-model="current_company" ></b-form-input><br>
                              <b-form-input type="text" id="current_location" placeholder="My current location" v-model="current_location" ></b-form-input><br>
                              <b-form-input type="text" id="degree" placeholder="My degree" v-model="degree" ></b-form-input>
                              </b-collapse>
                        </b-form-group>
                        <b-form-group id="skills_box">
                              <b-button href="#" v-b-toggle.accordion2 class="btn btn-sm btn-block" variant="outline-dark" id="btnskills">SKILLS</b-button>
                              <b-collapse id="accordion2" accordion="my-accordion" role="tabpanel"><br>
                              <b-form-input type="text" id="languages" placeholder="My languages" v-model="languages" class="onProgressbar" @focus="checkCompleted" ></b-form-input><br>
                              <b-form-input type="text" id="coding" placeholder="My programming skills" v-model="coding" ></b-form-input><br>
                              <b-form-input type="text" id="accomplishment" placeholder="My greatest accomplishment" v-model="accomplishment"></b-form-input><br>
                              <b-form-textarea type="text" id="about_me" rows="3" placeholder="About me" v-model="about_me" ></b-form-textarea><br>
                              <b-form-input type="text" id="salary" placeholder="My salary expectations" v-model="salary" ></b-form-input>
                              </b-collapse>
                       </b-form-group>
                       <b-form-group id="contact_box">
                              <b-button href="#" v-b-toggle.accordion3 class="btn btn-sm btn-block" variant="outline-dark" id="btncontact" >CONTACT</b-button>
                              <b-collapse id="accordion3" accordion="my-accordion" role="tabpanel"><br>
                              <b-form-input type="text" id="email"  placeholder="My email" v-model="email" class="onProgressbar" @focus="checkCompleted"></b-form-input><br>
                              <b-form-input type="text" id="phone"  placeholder="My phone number" v-model="phone"></b-form-input><br>
                              <b-form-input type="text" id="website"  placeholder="My website" v-model="website"></b-form-input><br>
                              <b-form-input type="text" id="linkedIn"  placeholder="My linkedIn account" v-model="linkedIn"></b-form-input><br>
                              <b-form-input type="text" id="address"  placeholder="My address" v-model="address"></b-form-input><br>
                              <b-form-input type="text" id="video" placeholder="My application video" v-model="video"></b-form-input>
                              </b-collapse>
                      </b-form-group>
                      <b-form-group id="application_box">
                              <b-button href="#" v-b-toggle.accordion4 class="btn btn-sm btn-block" variant="outline-dark" id="btnapplication">APPLICATION</b-button>
                              <b-collapse id="accordion4" accordion="my-accordion" role="tabpanel"><br>
                              <b-form-input type="text" id="desired_position" placeholder="Desired position" v-model="desired_position" class="onProgressbar" @focus="checkCompleted"></b-form-input>
                              </b-collapse>
                      </b-form-group>



            <div class="form-group">

              <b-button href="#" v-b-toggle.accordion5 class="btn btn-sm btn-block" variant="outline-dark" id="btnexperience">EXPERIENCE</b-button>

              <b-collapse id="accordion5" accordion="my-accordion" role="tabpanel">
              <div class="experience-box" id="urch">
                <input type="text" value="position" class="form-control" placeholder="Position" v-model="position1">
                <br>
                <input type="text" value="company" class="form-control" placeholder="Company" v-model="company1">
                <br>
                <input type="text" value="location" class="form-control" placeholder="Location" v-model="location1">
                <br>
                <input type="date" value="start" class="form-control" placeholder="Start MM.YYYY" v-model="startdate1">
                <br>
                <input type="date" value="end" class="form-control" placeholder="End MM.YYYY" v-model="enddate1">
                <br>
                <b-button class="btn btn-sm btn-block" :pressed.sync="btnpressed1" variant="outline-secondary" @click="iworkhere1">I currently work here</b-button>
                <br>
                <textarea type="text" value="tasks" class="form-control" rows="3" placeholder="My tasks" v-model="tasks1"></textarea>
              </div>

              <div id="shalalalala">
                <h6>{{ position1 }}</h6>
                <h6>{{ company1 }}</h6>
              </div>

              <div>
                  <b-button-group class="btn btn-sm btn-block" id="doublebutton">
                    <b-button variant="outline-success" @click="experience_done">OK</b-button>
                    <b-button variant="outline-dark" @click="add_experience">Add experience</b-button>
                  </b-button-group>
                </div>

              <div>
                <new-experience
                  v-for="experience in this.experiences"
                  :key="experience.id"
                  data="experience"
                  v-on:remove_experience="remove_experience(experience.id);"
                ></new-experience>
              </div>

              <hr class="hr">





            </b-collapse>
            </div>

            <div class="form-group">

              <b-button href="#" v-b-toggle.accordion6 class="btn btn-sm btn-block" variant="outline-dark" id="btneducation">EDUCATION</b-button>
              <b-collapse id="accordion6" accordion="my-accordion" role="tabpanel">
              <div id="education_box1">
                <br>
                <input type="text" value="study" class="form-control" placeholder="Study" v-model="study_s1">
                <br>
                <input type="text" value="institution" class="form-control" placeholder="Institution" v-model="institution_s1">
                <br>
                <input type="text" value="location" class="form-control" placeholder="Location" v-model="location_s1">
                <br>
                <input type="text" value="start" class="form-control" placeholder="Start MM.YYYY" v-model="startdate_s1">
                <br>
                <input type="text" value="end" class="form-control" placeholder="End MM.YYYY" v-model="enddate_s1">
                <br>
                <b-button class="btn btn-sm btn-block" :pressed.sync="btnpressed_s1" variant="outline-success" @click="istudyhere1">I currently study here</b-button>
                <br>
                <textarea type="text" value="achievements" class="form-control" rows="5" placeholder="My achievements" v-model="achievements_s1"></textarea>
              </div>
              <hr class="hr">
              <div id="education_box2">
                <br>
                <input type="text" value="study" class="form-control" placeholder="Study" v-model="study_s2">
                <br>
                <input type="text" value="institution" class="form-control" placeholder="Institution" v-model="institution_s2">
                <br>
                <input type="text" value="location" class="form-control" placeholder="Location" v-model="location_s2">
                <br>
                <input type="text" value="start" class="form-control" placeholder="Start MM.YYYY" v-model="startdate_s2">
                <br>
                <input type="text" value="end" class="form-control" placeholder="End MM.YYYY" v-model="enddate_s2">
                <br>
                <b-button class="btn btn-sm btn-block" :pressed.sync="btnpressed_s2" variant="outline-success" @click="istudyhere2">I currently study here</b-button>
                <br>
                <textarea type="text" value="achievements" class="form-control" rows="5" placeholder="My achievements" v-model="achievements_s2"></textarea>
              </div>
              <hr class="hr">
              <div id="education_box3">
                <br>
                <input type="text" value="study" class="form-control" placeholder="Study" v-model="study_s3">
                <br>
                <input type="text" value="institution" class="form-control" placeholder="Institution" v-model="institution_s3">
                <br>
                <input type="text" value="location" class="form-control" placeholder="Location" v-model="location_s3">
                <br>
                <input type="text" value="start" class="form-control" placeholder="Start MM.YYYY" v-model="startdate_s3">
                <br>
                <input type="text" value="end" class="form-control" placeholder="End MM.YYYY" v-model="enddate_s3">
                <br>
                <b-button class="btn btn-sm btn-block" :pressed.sync="btnpressed_s3" variant="outline-success" @click="istudyhere3">I currently study here</b-button>
                <br>
                <textarea type="text" value="achievements" class="form-control" rows="5" placeholder="My achievements" v-model="achievements_s3"></textarea>
              </div>
            </b-collapse>
            </div>

            <br>
          </b-form>
        </div>


      <div class="col-md-8">
        <div id="resumepage">
          <div id="full_nameview">
            <h4>{{ full_name }}</h4>
          </div>
          <div>
          <span class="inliner">
            <img src="../assets/media/icons/position.png" height="19px" v-if="current_position">
            <h6>&nbsp;&nbsp;&nbsp;{{ current_position }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/company.png" height="19px" v-if="current_company">
            <h6>&nbsp;&nbsp;&nbsp;{{ current_company }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/location.png" height="19px" v-if="current_location">
            <h6>&nbsp;&nbsp;&nbsp;{{ current_location }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/degree.png" height="19px" v-if="degree">
            <h6>&nbsp;&nbsp;&nbsp;{{ degree }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/languages.png" height="19px" v-if="languages">
            <h6>&nbsp;&nbsp;&nbsp;{{ languages }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/coding.png" height="19px" v-if="coding">
            <h6>&nbsp;&nbsp;&nbsp;{{ coding }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/accomplishment.png" height="19px" v-if="accomplishment">
            <h6>&nbsp;&nbsp;&nbsp;{{ accomplishment }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/about.png" height="19px" v-if="about_me">
            <h6>&nbsp;&nbsp;&nbsp;{{ about_me }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/salary.png" height="19px" v-if="salary">
            <h6>&nbsp;&nbsp;&nbsp;{{ salary }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner" id="emailview">
            <img src="../assets/media/icons/email.png" height="19px" v-if="email">
            <h6>&nbsp;&nbsp;&nbsp;{{ email }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner" id="phoneview">
            <img src="../assets/media/icons/phone.png" height="19px" v-if="phone">
            <h6>&nbsp;&nbsp;&nbsp;{{ phone }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/website.png" height="19px" v-if="website">
            <h6>&nbsp;&nbsp;&nbsp;{{ website }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/linkedin.png" height="19px" v-if="linkedIn">
            <h6>&nbsp;&nbsp;&nbsp;{{ linkedIn }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/address.png" height="19px" v-if="address">
            <h6>&nbsp;&nbsp;&nbsp;{{ address }}</h6>
          </span>
          </div>

          <div>
          <span class="inliner">
            <img src="../assets/media/icons/video.png" height="19px" v-if="video">
            <h6>&nbsp;&nbsp;&nbsp;{{ video }}</h6>
          </span>
          </div>

          <span v-if="email"><hr></span>

          <div id="WHYME">
          <span class="inliner">
            <img src="../assets/media/icons/application_black.png" height="24px" v-if="desired_position">
            <h6>&nbsp;&nbsp;&nbsp;{{ desired_position }}</h6>
          </span>
          </div>

          <span v-if="desired_position"><hr></span>

            <div class="row">

              <div class="col-md-6">
                <div id="experience_headline">
                  <h6 v-if="position1">EXPERIENCE</h6>
                </div>
                <br>

                <div id="experience1">
                  <div class="position">
                    <h6>{{ position1 }}</h6>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/company_black.png" height="19px" v-if="company1">
                      <h6>&nbsp;{{ company1 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/location_black.png" height="19px" v-if="location1">
                      <h6>&nbsp;{{ location1 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/calendar_black.png" height="19px" v-if="startdate1 || enddate1 || noend1">
                      <h6>&nbsp;{{ period1 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/tasks_black.png" height="19px" v-if="tasks1">
                      <h6>&nbsp;{{ tasks1 }}</h6>
                    </span>
                  </div>
                </div>
                <br>



                <br>

                <br>
              </div>




              <div class="col-md-6">
                <div id="education_headline">
                  <h6 v-if="study_s1">EDUCATION</h6>
                </div>
                <br>

                <div id="education1">
                  <div class="study">
                    <h6>{{ study_s1 }}</h6>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/institution.png" height="19px" v-if="institution_s1">
                      <h6>&nbsp;{{ institution_s1 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/location_black.png" height="19px" v-if="location_s1">
                      <h6>&nbsp;{{ location_s1 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/calendar_black.png" height="19px" v-if="startdate_s1 || enddate_s1 || noend_s1">
                      <h6>&nbsp;{{ period_s1 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/achievements.png" height="19px" v-if="achievements_s1">
                      <h6>&nbsp;{{ achievements_s1 }}</h6>
                    </span>
                  </div>
                </div>
                <br>
                <div id="education2">
                  <div class="study">
                    <h6>{{ study_s2 }}</h6>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/institution.png" height="19px" v-if="institution_s2">
                      <h6>&nbsp;{{ institution_s2 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/location_black.png" height="19px" v-if="location_s2">
                      <h6>&nbsp;{{ location_s2 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/calendar_black.png" height="19px" v-if="startdate_s2 || enddate_s2 || noend_s2">
                      <h6>&nbsp;{{ period_s2 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/achievements.png" height="19px" v-if="achievements_s2">
                      <h6>&nbsp;{{ achievements_s2 }}</h6>
                    </span>
                  </div>
                </div>
                <br>
                <div id="education3">
                  <div class="study">
                    <h6>{{ study_s3 }}</h6>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/institution.png" height="19px" v-if="institution_s3">
                      <h6>&nbsp;{{ institution_s3 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/location_black.png" height="19px" v-if="location_s3">
                      <h6>&nbsp;{{ location_s3 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/calendar_black.png" height="19px" v-if="startdate_s3 || enddate_s3 || noend_s3">
                      <h6>&nbsp;{{ period_s3 }}</h6>
                    </span>
                  </div>

                  <div>
                    <span class="inliner">
                      <img src="../assets/media/icons/achievements.png" height="19px" v-if="achievements_s3">
                      <h6>&nbsp;{{ achievements_s3 }}</h6>
                    </span>
                  </div>
                </div>
                <br>
              </div>
            </div>
          </div>
          </div>
        </div>
        <hr>
        <div class="row">
          <div class="col signupResume">
            <button type="button" class="btn btn-sm btn-pantone">Sign Up</button>
            <span>*</span>
           </div>
           <div class="col pdf-reset">
             <button type="button" class="btn btn-sm btn-outline-dark" @click="exportPdf">Create pdf</button>
             <button type="button" class="btn btn-sm btn-outline-danger" @click="resetResume">Reset</button>
           </div>
         </div>
        <hr>
        <div id="signupExplanation">
          <p>* Sign up to get your personal Nayaca account. As a user you can keep your data, choose from our beautiful color designs and edit your resume any time to match
            new positions in the blink of an eye. If you are already a registered user, click the 'Sign Up' button to sign in.</p>

        </div>
      </div>
    <the-footer/>
</div>
</template>

<script>
    import TheFooter from '../components/TheFooter';
    import NewExperience from '../components/NewExperience';
    //Progress bar dependencies
    import VueFocus from 'vue-focus';
    import $ from 'jquery';
    //Js to PDF dependencies
    import jsPDF from 'jspdf';
    import html2canvas from 'html2canvas';


export default {
  name: 'resume',
  components: {
      'the-footer': TheFooter,
      'new-experience':  NewExperience, // eslint-disable-next-line
      VueFocus, // eslint-disable-next-line
      html2canvas
  },
  data() {
    return {
      full_name: '',
      current_position: '',
      current_company: '',
      current_location: '',
      about_me: '',
      accomplishment: '',
      coding: '',
      degree: '',
      languages: '',
      salary: '',
      email: '',
      phone: '',
      website: '',
      linkedIn: '',
      address: '',
      video: '',
      desired_position: '',
      position1: '',
      company1: '',
      location1: '',
      startdate1: '',
      enddate1: '',
      noend1: false,
      tasks1: '',
      current_index: 0,
      experiences: [],
      exp_id: 0,
      position: '',
      company: '',
      location: '',
      startdate: '',
      enddate: '',
      noend: false,
      tasks: '',
      position3: '',
      company3: '',
      location3: '',
      startdate3: '',
      enddate3: '',
      noend3: false,
      tasks3: '',
      study_s1: '',
      institution_s1: '',
      location_s1: '',
      startdate_s1: '',
      enddate_s1: '',
      noend_s1: false,
      achievements_s1: '',
      study_s2: '',
      institution_s2: '',
      location_s2: '',
      startdate_s2: '',
      enddate_s2: '',
      noend_s2: false,
      achievements_s2: '',
      study_s3: '',
      institution_s3: '',
      location_s3: '',
      startdate_s3: '',
      enddate_s3: '',
      noend_s3: false,
      achievements_s3: '',
      btnpressed1: false,
      btnpressed2: false,
      btnpressed3: false,
      btnpressed_s1: false,
      btnpressed_s2: false,
      btnpressed_s3: false,
      //progress bar key-value pairs
      maxbar: 100,
      valuebar: 0

}
  },

  computed: {
/*    currently: function() {
  if (this.current_position && this.current_company && this.current_location) {
    return this.current_position + ' | ' + this.current_company + ' | ' + this.current_location;
  } else if (this.current_position && this.current_company) {
    return this.current_position + ' | ' + this.current_company;
  } else if (this.current_position && this.current_location) {
    return this.current_position + ' | ' + this.current_location;
  } else if (this.current_company && this.current_location) {
    return this.current_company + ' | ' + this.current_location;
  } else {
    return this.current_position || this.current_company || this.current_location;
  }
},*/
    period1() {
      if (this.startdate1 && this.enddate1 && this.noend1) {
        return 'since ' + this.startdate1;
      } else if (this.startdate1 && this.enddate1) {
        return this.startdate1 + ' - ' + this.enddate1;
      } else if (this.startdate1 && this.noend1) {
        return 'since ' + this.startdate1;
      } else if (this.enddate1 && this.noend1) {
        return null;
      } else if (this.startdate1) {
        return 'since ' + this.startdate1;
      } else if (this.enddate1) {
        return 'until ' + this.enddate1;
      } else if (this.noend1) {
        return 'I currently work here.';
      } else {
        return null;
      }
    },

    period2() {
      if (this.startdate2 && this.enddate2 && this.noend2) {
        return 'since ' + this.startdate2;
      } else if (this.startdate2 && this.enddate2) {
        return this.startdate2 + ' - ' + this.enddate2;
      } else if (this.startdate2 && this.noend2) {
        return 'since ' + this.startdate2;
      } else if (this.enddate2 && this.noend2) {
        return null;
      } else if (this.startdate2) {
        return 'since ' + this.startdate2;
      } else if (this.enddate2) {
        return 'until ' + this.enddate2;
      } else if (this.noend2) {
        return 'I currently work here.';
      } else {
        return null;
      }
    },

    period3() {
      if (this.startdate3 && this.enddate3 && this.noend3) {
        return 'since ' + this.startdate3;
      } else if (this.startdate3 && this.enddate3) {
        return this.startdate3 + ' - ' + this.enddate3;
      } else if (this.startdate3 && this.noend3) {
        return 'since ' + this.startdate3;
      } else if (this.enddate3 && this.noend3) {
        return null;
      } else if (this.startdate3) {
        return 'since ' + this.startdate3;
      } else if (this.enddate3) {
        return 'until ' + this.enddate3;
      } else if (this.noend3) {
        return 'I currently work here.';
      } else {
        return null;
      }
    },

    period_s1() {
      if (this.startdate_s1 && this.enddate_s1 && this.noend_s1) {
        return 'since ' + this.startdate_s1;
      } else if (this.startdate_s1 && this.enddate_s1) {
        return this.startdate_s1 + ' - ' + this.enddate_s1;
      } else if (this.startdate_s1 && this.noend_s1) {
        return 'since ' + this.startdate_s1;
      } else if (this.enddate_s1 && this.noend_s1) {
        return null;
      } else if (this.startdate_s1) {
        return 'since ' + this.startdate_s1;
      } else if (this.enddate_s1) {
        return 'until ' + this.enddate_s1;
      } else if (this.noend_s1) {
        return 'I currently study here.';
      } else {
        return null;
      }
    },

    period_s2() {
      if (this.startdate_s2 && this.enddate_s2 && this.noend_s2) {
        return 'since ' + this.startdate_s2;
      } else if (this.startdate_s2 && this.enddate_s2) {
        return this.startdate_s2 + ' - ' + this.enddate_s2;
      } else if (this.startdate_s2 && this.noend_s2) {
        return 'since ' + this.startdate_s2;
      } else if (this.enddate_s2 && this.noend_s2) {
        return null;
      } else if (this.startdate_s2) {
        return 'since ' + this.startdate_s2;
      } else if (this.enddate_s2) {
        return 'until ' + this.enddate_s2;
      } else if (this.noend_s2) {
        return 'I currently study here.';
      } else {
        return null;
      }
    },

    period_s3() {
      if (this.startdate_s3 && this.enddate_s3 && this.noend_s3) {
        return 'since ' + this.startdate_s3;
      } else if (this.startdate_s3 && this.enddate_s3) {
        return this.startdate_s3 + ' - ' + this.enddate_s3;
      } else if (this.startdate_s3 && this.noend_s3) {
        return 'since ' + this.startdate_s3;
      } else if (this.enddate_s3 && this.noend_s3) {
        return null;
      } else if (this.startdate_s3) {
        return 'since ' + this.startdate_s3;
      } else if (this.enddate_s3) {
        return 'until ' + this.enddate_s3;
      } else if (this.noend_s3) {
        return 'I currently study here.';
      } else {
        return null;
      }
    }

  },
  methods: {
    iworkhere1() {
      this.noend1 = !this.noend1;
    },
    iworkhere2() {
      this.noend2 = !this.noend2;
    },
    iworkhere3() {
      this.noend3 = !this.noend3;
    },
    istudyhere1() {
      this.noend_s1 = !this.noend_s1;
    },
    istudyhere2() {
      this.noend_s2 = !this.noend_s2;
    },
    istudyhere3() {
      this.noend_s3 = !this.noend_s3;
    },
    // Input & Progress Bar Tracking with vue-focus https://github.com/simplesmiler/vue-focus
    // just had to pull in a vue-focus event other than vue and jQuery
    checkCompleted: function() {
      // find all inputs
      var totalInputs = $('input.onProgressbar').length;

      var filledInputs = 0;
      $('input.onProgressbar').each(function() {
        // has a value
        if ((this.value)) {
          filledInputs++;
        }
      });

      // do the math
      var find = filledInputs / totalInputs * 100;

      // update local variable in Vue data
      this.valuebar = Math.round(find);
    },

  ready: function() {
    // check for any existing values on page load, set accordingly
    this.checkCompleted();
  },


  //New jsPDF working and to be improved
  exportPdf() {
    const doc = new jsPDF("p", "pt", "a4", true);

    doc.fromHTML($('#resumepage')[0], 15, 15, {
              'width': 1000,
          },
              function () {
                  doc.save('myNayaca.pdf');
                  window.open(doc.output('bloburl')); // To debug.
              }
          );

  },

    resetResume() {
      this.full_name = '',
      this.current_position = '',
      this.current_company = '',
      this.current_location = '',
      this.about_me = ''
    },
    add_experience() {
      this.exp_id++;
      this.experiences.push({
        id: this.exp_id
      });
    },
    remove_experience(id) {
      for (var i = this.experiences.length; i--; ) {
        if (this.experiences[i].id !== id) continue;
        this.experiences.splice(i, 1);
        return;
      }
    },
    experience_done() {
      $('#urch').hide();
     $('#shalalalala').show();
   },
  }
}



window.addEventListener("scroll", function() {
    if (pageYOffset > 100) {
      $(".navbar-brand").hide();
    } else {
      $(".nayaca-text").show();
}
});

</script>

<style lang="scss">
  @import '../modules/resume.css';
</style>
