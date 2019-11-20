<template>
  <div id="nav">
    <img src="../assets/peexooLogo.png" class="pLogo" />
    <div class="nav-link-container">
      <a>I am a photographer</a>
      <a>Explore photos</a>
      <a>Find a photographer</a>
      <a>Find my photos</a>
      <a>Login or Register</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav'
}
</script>

<style>
#nav{
width: 100vw;
height: 80px;
display: flex;
flex-direction: row;
align-items: center;
}
.pLogo {
position: absolute;
width: 120px;
left: 50px;
filter: invert(79%) sepia(19%) saturate(6857%) hue-rotate(358deg) brightness(102%) contrast(105%);
}
.nav-link-container {
position: absolute;
display: flex;
flex-direction: row;
align-items: center;
justify-content: space-between;
width: 50%;
right: 50px;
}
.nav-link-container > a {
cursor: pointer;
font-size: 15px;
color: #000
}
.nav-link-container> a:hover {
color: #B58000;
}
.nav-link-container > a:last-child{
color: #B58000;
}
.nav-link-container > a:last-child:hover{
color: #000;
}

</style>
