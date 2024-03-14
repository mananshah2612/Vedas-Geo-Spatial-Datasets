<template>
  <div class="pdm-container">
    <div class="top-container">
      <div class="logo">
        <img src="../assets/vedas.png" alt="vedas logo" />
      </div>
      <div class="user">
        <img class="user-button" src="../assets/user.png" alt="user-image" />
      </div>
    </div>
    <div class="mid-container">
      <div class="heading">
        <h1>Primary Data Mangement</h1>
      </div>
      <div class="back">
        <button @click="$router.push('/primary-data-main-page')">
          <i class="fa-solid fa-arrow-left" id="back-arrow"></i>
          <p class="text-back">Back</p>
        </button>
      </div>
      <div class="form-containers">
        
      <transition  name="slide-fade">
        <div class="form-container-1" v-show="showFormContainerOne">
        <FormContainerOne :subtheme="subtheme" :theme="theme" @validate-and-proceed="ExtraFormHandleValidationAndProceed" />
      </div>
      </transition>
   
         
      <transition name="extra-form-slide-fade">
         <div class="extra-cont" v-if="showExtraFormContainer">
        <ExtraFormContainer ref="formContainerOne" :subtheme="subtheme" :theme="theme" @validate-and-proceed="handleValidationAndProceed" @MoveBackToOne="handleMoveBackToOne"/>
      </div>
      </transition>
   
        <div class="form-container-2">
          <FormContainerTwo v-if="showFormContainerTwo " :theme="theme" :subtheme="subtheme" @validate-and-proceed-second-form="FormTwoHandleValidationAndProceed" @MoveBackToExtra = "handleMoveBackToExtra" />
        </div>
        <div class="form-container-3">
          <FormContainerThree v-if="showFormContainerThree" @validate-and-proceed-form-three="FormThreeHandleValidationAndProceed" @MoveBackToTwo = "handleMoveBackToTwo" />
        </div>
        <div class="form-container-4">
          <FormContainerFour v-if="showFormContainerFour" @validate-and-proceed-form-four="FormFourHandleValidationAndProceed" @MoveBackToThree= "handleMoveBackToThree"/>
        </div>
        <div class="form-container-5">
          <FormContainerFive v-if="showFormContainerFive" @validate-and-proceed-form-five="FormFiveHandleValidationAndProceed" @MoveBackToFour = "handleMoveBackToFour" />
        </div>
        <div class="form-container-6">
          <FormContainerSix v-if="showFormContainerSix" @validate-and-proceed-form-six="FormSixHandleValidationAndProceed" @MoveBackToFive = "handleMoveBackToFive"/>
        </div>
        <div class="form-container-7">
          <FormContainerSeven v-if="showFormContainerSeven" @validate-and-proceed-form-seven="FormSevenHandleValidationAndProceed" @MoveBackToSix = "handleMoveBackToSix" />
        </div>
        <div class="form-container-8">
          <FormContainerEight v-if="showFormContainerEight" @validate-and-proceed-form-eight="FormEightHandleValidationAndProceed" @MoveBackToSeven = "handleMoveBackToSeven"/>
        </div>
        <div class="form-container-9">
          <FormContainerNine v-if="showFormContainerNine" @validate-and-proceed-form-nine="FormNineHandleValidationAndProceed" @MoveBackToEight= "handleMoveBackToEight"/>
        </div>
        <div class="form-container-10">
          <FormContainerTen v-if="showFormContainerTen" @validate-and-proceed-form-ten="FormTenHandleValidationAndProceed" @MoveBackToNine = "handleMoveBackToNine"/>
        </div>
        <div class="form-container-11">
          <FormContainerEleven v-if="showFormContainerEleven" @MoveBackToTen = "handleMoveBackToTen" />
          <div class="submit-button" v-show="showFormContainerEleven">
          <button>Submit</button>
        </div>
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
import FormContainerOne from "../components/FormContainerOne.vue";
import ExtraFormContainer from "../components/ExtraFormContainer.vue";
import FormContainerTwo from "../components/FormContainerTwo.vue";
import FormContainerThree from "../components/FormContainerThree.vue";
import FormContainerFour from "../components/FormContainerFour.vue";
import FormContainerFive from "../components/FormContainerFive.vue";
import FormContainerSix from '../components/FormContainerSix.vue'
import FormContainerSeven from "../components/FormContainerSeven.vue";
import FormContainerEight from "../components/FormContainerEight.vue";
import FormContainerNine from '../components/FormContainerNine.vue'
import FormContainerTen from '../components/FormContainerTen.vue'
import FormContainerEleven from "../components/FormContainerEleven.vue";

export default {
  data() {
    return {
      
      showFormContainerOne: true,
      showFormContainerTwo: false,
      showExtraFormContainer: false,
      showFormContainerThree: false,
      showFormContainerFour: false,
      showFormContainerFive: false,
      showFormContainerSix: false,
      showFormContainerSeven: false,
      showFormContainerEight: false,
      showFormContainerNine: false,
      showFormContainerTen:false,
      showFormContainerEleven:false,
      theme: "",
      subtheme: "",
      BasePath: "",
      
      
    };
  },
  name: "primary-data-management",
  components: {
    FormContainerOne,
    ExtraFormContainer,
    FormContainerTwo,
    FormContainerThree,
    FormContainerFour,
    FormContainerFive,
    FormContainerSix,
    FormContainerSeven,
    FormContainerEight,
    FormContainerNine,
    FormContainerTen,
    FormContainerEleven,
  },
  methods: {

    handleMoveBackToOne(){
      this.showFormContainerOne = true;
      this.showExtraFormContainer = false;
    },

    handleMoveBackToExtra(){
      this.showExtraFormContainer = true;
      this.showFormContainerTwo = false;
    },
     handleMoveBackToTwo(){
      this.showFormContainerTwo = true;
      this.showFormContainerThree = false;
    },
     handleMoveBackToThree(){
      this.showFormContainerThree = true;
      this.showFormContainerFour = false;
    },
    handleMoveBackToFour(){
      this.showFormContainerFour = true;
      this.showFormContainerFive = false;
    },
    handleMoveBackToFive(){
      this.showFormContainerFive = true;
      this.showFormContainerSix = false;
    },
    handleMoveBackToSix(){
      this.showFormContainerSix = true;
      this.showFormContainerSeven = false;
    },
    handleMoveBackToSeven(){
      this.showFormContainerSeven = true;
      this.showFormContainerEight = false;
    },
    handleMoveBackToEight(){
      this.showFormContainerEight = true;
      this.showFormContainerNine = false;
    },
   handleMoveBackToNine(){
      this.showFormContainerNine = true;
      this.showFormContainerTen = false;
    },
    handleMoveBackToTen(){
      this.showFormContainerTen = true;
      this.showFormContainerEleven = false;
    },
    
    
    ExtraFormHandleValidationAndProceed() {
       this.showFormContainerOne = false;
      this.showExtraFormContainer = true;
    },
    handleValidationAndProceed(subtheme, theme) {
      console.log("Theme value:", theme); 
      this.subtheme = subtheme;
      this.theme = theme; // Set the value of theme here
      this.showExtraFormContainer = false
      this.showFormContainerTwo = true;
    },
    FormTwoHandleValidationAndProceed() {
      this.showFormContainerTwo= false;
      this.showFormContainerThree = true;
    },
    FormThreeHandleValidationAndProceed() {
      this.showFormContainerThree = false;
      this.showFormContainerFour = true;
    },
    FormFourHandleValidationAndProceed(){
      this.showFormContainerFour = false;
      this.showFormContainerFive = true;
    },
    FormFiveHandleValidationAndProceed(){
      this.showFormContainerFive = false;
      this.showFormContainerSix = true;
    },
    FormSixHandleValidationAndProceed(){
      this.showFormContainerSix = false;
      this.showFormContainerSeven = true;
    },
    FormSevenHandleValidationAndProceed(){
      this.showFormContainerSeven = false;
      this.showFormContainerEight = true;
    },
    FormEightHandleValidationAndProceed(){
      this.showFormContainerEight = false;
      this.showFormContainerNine = true;
    },
    FormNineHandleValidationAndProceed(){
      this.showFormContainerNine = false;
      this.showFormContainerTen = true;
    },
    FormTenHandleValidationAndProceed(){
      this.showFormContainerTen = false;
      this.showFormContainerEleven = true;
    },
  }
};
</script>
<style scoped>
body,
html {
  margin: 0;
  padding: 0;
  height: 100%;
  
  
}

button {
  --clr-font-main: hsla(0 0% 20% / 100);
  --btn-bg-1: hsla(194 100% 69% / 1);
  --btn-bg-2: hsla(217 100% 56% / 1);
  --btn-bg-color: hsla(360 100% 100% / 1);
  --radii: 0.5em;
  cursor: pointer;
  
  min-width: 120px;
  min-height: 44px;
  font-size: var(--size, 1rem);
  font-family: "Segoe UI", system-ui, sans-serif;
  font-weight: 500;
  transition: 0.8s;
  background-size: 280% auto;
  background-image: linear-gradient(325deg, var(--btn-bg-2) 0%, var(--btn-bg-1) 55%, var(--btn-bg-2) 90%);
  border: none;
  width: 50px;
  border-radius: var(--radii);
  color: var(--btn-bg-color);
  box-shadow: 0px 0px 20px rgba(71, 184, 255, 0.5), 0px 5px 5px -1px rgba(58, 125, 233, 0.25), inset 4px 4px 8px rgba(175, 230, 255, 0.5), inset -4px -4px 8px rgba(19, 95, 216, 0.35);
}

button:hover {
  background-position: right top;
}



button:is(:focus, :focus-visible, :active) {
  outline: none;
  box-shadow: 0 0 0 3px var(--btn-bg-color), 0 0 0 6px var(--btn-bg-2);
}

@media (prefers-reduced-motion: reduce) {
  button {
    transition: linear;
  }
}

.submit-button button{
  display: flex;
  justify-content:center;
  align-items: center;
}

.submit-button{
  display: flex;
  justify-content:center;
  align-items: center;
  position: relative;
  
}


#back-arrow{
  position: relative;
  top: 18px;
  left: 18px;
  font-size: 22px;
}
.top-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  padding: 0;
  background: inherit;
  display: flex;
  justify-content: space-between;
}

.logo {
  margin-right: 20px; /* Add some spacing between the logo and other content */
  position: fixed;
}

.logo img {
  margin-left: 20px;
}

.user-button {
  width: 80px;
  margin: 33px;
  border-radius: 50%; /* Add rounded corners */
  box-shadow: 0px 1px 5px rgb(94, 77, 77);
  position: fixed;
  right: 0
}

.form-container-6{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  
}


.user-button:hover {
  box-shadow: 0px 0px 0px rgb(94, 77, 77);
  cursor: pointer;
  z-index: 20;
}

.user-button {
  --clr-font-main: hsla(0 0% 20% / 100);
  --btn-bg-1: rgb(65, 145, 249);
  --btn-bg-2: hsla(194 100% 56% / 1);
  --btn-bg-color: hsla(360 100% 100% / 1);
  --radii: 0.5em;
  cursor: pointer;
  min-width: 120px;
  
  font-size: var(--size, 1rem);
  font-family: "Segoe UI", system-ui, sans-serif;
  font-weight: 500;
  transition: 0.8s;
  background-size: 280% auto;
  border: none;
  width: 50px;
  border-radius: 50%;
  color: var(--btn-bg-color);
  box-shadow: 0px 0px 20px rgba(71, 184, 255, 0.5), 0px 5px 5px -1px rgba(58, 125, 233, 0.25), inset 4px 4px 8px rgba(175, 230, 255, 0.5), inset -4px -4px 8px rgba(19, 95, 216, 0.35);
}

.user-button:hover {
  background-position: right top;
}

.user-button:is(:focus, :focus-visible, :active) {
  outline: none;
  box-shadow: 0 0 0 3px var(--btn-bg-color), 0 0 0 6px var(--btn-bg-2);
}


@media (prefers-reduced-motion: reduce) {
  .user-button {
    transition: linear;
  }
}

.pdm-container {
  padding-top:130px ;
  display: flex;
  justify-content: center;
  align-items: stretch;
  height: 150vh;
  width: 100%;
  background: linear-gradient(
    to right,
    #c3e5f9,
    #bae1f6,
    #b0dcf3,
    #a6d8f0,
    #9cd4ed,
    #93d1eb,
    #89cde8,
    #7fcae6,
    #73c6e4,
    #67c2e3,
    #59bee1,
    #49bae0
  ); /* Gradient background */
}

button img {
  width: 30px;
  margin-top: 5px;
}


.form-containers {
  display: flex;
  /* Allow containers to wrap to the next line */
  justify-content: flex-start; /* Align containers to the start of the line */
  position: relative;
  justify-content: space-between;
}

.text-back{
  position: relative;
  top: 0.7px;
  right: 20px;
  font-size: 16px;
  
}

.back button{
  left: 20%;
}

button {
  display: flex;
  justify-content: space-between;
  width: 90px;
  margin: 33px;
  border-radius: 50px; /* Add rounded corners */
  box-shadow: 0px 1px 5px rgb(94, 77, 77);
  margin-bottom: 20px;
  margin-top: 20px;
  position: relative;
  
}




.form-containers {
  display: flex;
  
  position: relative;
  justify-content: center;
  align-items: center;
  left: 23%;
  
}


.slide-fade-enter-active, .slide-fade-leave-active {
  transition: all 0.5s ease;
}

.slide-fade-enter, .slide-fade-leave-to /* .slide-fade-leave-active in <2.1.8 */ {
  opacity: 0;
  transform: translateY(-20px);
}

.extra-form-slide-fade-enter-active, .extra-form-slide-fade-leave-active {
  transition: all 0.5s ease;
}

.extra-form-slide-fade-enter, .extra-form-slide-fade-leave-to /* .extra-form-slide-fade-leave-active in <2.1.8 */ {
  opacity: 0;
  transform: translateY(-20px); /* You can adjust the translateY value as per your preference */
}

.form-container-1,.form-container-2,.form-container-3,.form-container-6,.form-container-4,.form-container-5,.form-container-6,.form-container-7,.form-container-8,.form-container-9,.form-container-10,.form-container-11{
  z-index: 999;
  padding: 15px;
}

.form-container-3{
  position: relative;
  right: 70px;
}
.form-container-2{
  position: relative;
  right: 68px;
}

.form-container-1{
  position: relative;
  right: 68px;
}

.extra-cont{
  position: relative;
  right: 70px;
}

.form-container-4{
  position: relative;
  right: 68px;
}

.form-container-5{
  position: relative;
  right: 85px;
}

.form-container-6{
  position: relative;
  right: 68px;
}
.form-container-7{
  position: relative;
  right: 214px;
}
.form-container-8{
  position: relative;
  right: 284px;
}
.form-container-9{
  position: relative;
  right: 286px;
}
.form-container-10{
  position: relative;
  right: 293px;
}
.form-container-11{
  position: relative;
  right: 322px;
}
</style>
