<template>
    <nav class="banner">
        <a @click="openLinkNewTab" class="logo-container">
            <img class="vis-logo" src="./VisualisationsLogoWhite2.png">
        </a>
        <div class="vis-title"><slot>Default Title</slot></div>
    </nav>
    
</template>

<script>
export default {
    name:"iv-title-bar",
    props:{
      buttonLink:{
        type: String,
        default: "https://www.imperialvisualisations.com/learn/"
      },
      newTab:{
        type: Boolean,
        default: true
      }
    },
    methods:{
        openLinkNewTab: function () {
          if (this.newTab){
            window.open(this.buttonLink, "_blank");
          } else{
            open(this.buttonLink, "_self");
          }
        }
    }
}
</script>

<style>

.banner {
  display: flex;
  flex: 0 0 auto;
  justify-content: flex-end;
  align-items: center;
  padding: 0.25rem 0rem;
  width: 100%;
  position: fixed; 
  top: 0;
  right: 0;
  background: linear-gradient(
          90deg,
          #003E74 0%,
          #37578b 15%,
          #37578b 100%
  );
  color: #ffffff;
  z-index: 6;
}

.vis-title {
  flex-basis: 0;
  flex-grow: 1;
  margin:0;
  padding: 0;
  position: fixed;
  text-align: center;
  font-weight: bolder;
  left: 0vw;
  right: 0;
  background: none;
  color: #ffffff;
  font-size: 1.5rem;
  line-height: 1.5rem;
}

.logo-container {
  color: #1EAEDB; 
  z-index: 10;
  cursor: pointer;
  display:block;
  padding:0;
  height:1.5rem;

}

.logo-container:hover {
  color: #0FA0CE; }

.vis-logo {
  height: 1.25rem;
  width:auto;
  margin: 0.125rem 0.25rem;
}

</style>