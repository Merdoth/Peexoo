<template>
  <div id="dash">
    <img src="../assets/apples.jpeg" class="dash-img"/>
    <div class="dash-content-links">
      <div class="dash-routes">
        <a>Details</a>
        <a>Portfolio</a>
        <a>Availability</a>
        <a>Pricing packages</a>
        <a>Reviews</a>
      </div>
    </div>
    <div class="dash-content-profile">
      <div class="dash-profile-img">
        <img src="../assets/camera-girl.jpeg">
        <div class="dash-profile-header">
          <p>Afroshots</p>
          <img src="../assets/tick-tick.jpeg"/>
        </div>
      </div>
    </div>
    <div class="dash-button">
     <button>Message Photographer</button>
     <button>Book Now</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Dash',
}
</script>

<style>
#dash, .dash-content-link, .dash-routes,
.dash-profile-header, .dash-button {
display: flex;
flex-direction: row;
}
#dash, .dash-img, .dash-content-links, .dash-routes ,
.dash-content-profile,  .dash-profile-header, .dash-button
{
position: absolute;
}

#dash {
top: 80px;
width: 100vw;
height: 75%;
}
.dash-img {
 width: 100%;
 height: 700px;
 object-fit: cover;
}
.dash-content-links {
background: #de9c00;
width: 100%;
height: 70px;
bottom: 0;
}
.dash-routes {
color: #fff;
right: 150px;
width: 60%;
justify-content: space-between;
}
.dash-routes > a {
width: 140px;
text-align: center;
padding: 25px 0px;
cursor: pointer;
font-size: 15px;
}
.dash-routes > a:hover {
  background-color: #4d4d4d;
}
.dash-content-profile {
display: flex;
flex-direction: column;
width: 260px;
height: 260px;
bottom: -95px;
left: 150px;
}
.dash-profile-img {
margin-top: 5px;
margin-left: 5px;
width: 160px;
height: 180px;
border-radius: 5px;
}
.dash-profile-img > img {
width: 160px;
height: 180px;
object-fit: cover;
border-radius: 5px;
}
.dash-profile-header > p {
font-size: 40px;
letter-spacing: 1px;
font-weight: 400;
font-family: 'Calistoga', cursive;
color: #4d4d4d;
margin-top: 5px;
}
.dash-profile-header > img {
margin-top: 18px;
margin-left: 10px;
width: 30px;
height: 30px;
object-fit: cover;
}
.dash-button {
width: 25%;
height: 45px;
bottom: -90px;
right: 150px;
justify-content: space-around;
}
.dash-button > button {
background: #fefbf3;
width: 200px;
border-radius: 50px;
border: 1px solid #ffb505;
color: #ffb505;
font-size: 14px;
cursor: pointer;
outline: none;
}
.dash-button > button:hover {
background: #ffb505;
color: #fff;
}
</style>
