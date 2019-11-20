<template>
  <div id="footer">
    <div class="footer-top">
      <div class="footer-links">
          <p class="footer-header">Quick Links</p>
          <a>Find a photograher</a>
          <a>Find my photos</a>
          <a>Peexoomemories</a>
          <a>Become a photograher</a>
      </div>
      <div class="footer-links">
          <p class="footer-header">Company</p>
          <a>About Us</a>
          <a>FAQs</a>
          <a>Pricing</a>
          <a>Careers</a>
          <a>Help & Support</a>
          <a>Terms of Service</a>
          <a>Privacy Policy</a>
      </div>
      <div class="footer-links">
          <p class="footer-header address-header">Connect with us</p>
          <span class="address"><p>5A, Awudu Egheda,</p><p>Lekki, Lagos,</p> <p>+234 8003229932 </p><p>customers.service@peexoo.ai</p></span>
          <div class="footer-icons">
          <img src="../assets/WhatsApp.png"/>
          <img src="../assets/Facebook.png"/>
          <img src="../assets/twitter.png"/>
          <img src="../assets/Instagram.png"/>
          </div>
      </div>
    </div>
   <div class="footer-bottom">
       <p>@ 2019 Peexo Nigeria Limited</p>
   </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
}
</script>

<style>
#footer, .footer-top, .footer-bottom, .footer-icons {
position: absolute;
}
#footer, .footer-top, .footer-icons {
display: flex;
flex-direction: row;
}

#footer {
top: 163%;
width: 100vw;
height: 40%;
}
.footer-top {
width: 70%;
color: #4d4d4d;
justify-content: space-around;
margin: 0 auto;
left: 0;
right: 0;
top: 40px;
}
.footer-links {
display: flex;
flex-direction: column;
}
.footer-header {
font-size: 16px;
font-weight: 900;
}
.footer-links  > a, .address > p {
font-size: 15px;
margin-bottom: 10px;
letter-spacing: .5px;
}
.footer-links > a:hover {
color: #B58000;
cursor: pointer;
}
.address-header {
margin-bottom: 5px;
}
.footer-icons {
top: 200px;
}
.footer-icons > img{
width: 20px;
height: 20px;
object-fit: contain;
margin-right: 5px;
cursor: pointer;
}
.footer-bottom {
background: #202020;
color: #fefbf3;
width: 100vw;
height: 50px;
bottom: 0%;
text-align: center;
font-size: 14px;
}
</style>
