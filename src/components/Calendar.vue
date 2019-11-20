<template>
  <div id="calendar">
   <div class="calendar-container july">
      <div class="calendar-header">
          <span class="calendar-month">July</span>
      </div>
        <div class="date">
              <div class="day_name" v-for="(day, index) in days" :key="index">
              {{day}}
          </div>
           <div id="augustDay" class="days"></div> 
          <div :id="`disabled${index}`" @click="disabled(index)" class="days" v-for="(monthDay, index) in monthDays.july" :key="index">
              {{monthDay}}
          </div>
      </div>
   </div>
   <div class="calendar-container august">
      <div class="calendar-header">
          <span class="calendar-month">August</span>
      </div>
      <div class="date">
              <div class="day_name" v-for="(day, index) in days" :key="index">
              {{day}}
          </div>
           <div id="augustDay" class="days"></div> 
           <div id="augustDay" class="days"></div>
           <div id="augustDay" class="days"></div>
           <div id="augustDay" class="days"></div>
          <div :id="`disabled${index}`" @click="disabled(index)" class="days" v-for="(monthDay, index) in monthDays.august" :key="index">
              {{monthDay}}
          </div>
      </div>
   </div>
   <div class="calendar-container september">
      <div class="calendar-header">
          <span class="calendar-month">September</span>
      </div>
        <div class="date">
              <div class="day_name" v-for="(day, index) in days" :key="index">
              {{day}}
          </div>
          <div :id="`disabled${index}`" @click="disabled(index)" class="days" v-for="(monthDay, index) in monthDays.september" :key="index">
              {{monthDay}}
          </div>
      </div>
   </div>
   <div class="calendar-navigation">
     <div class="greater-than">
        <p></p>
        <p></p>
     </div>
     <div class="inner-circle"></div>
     <div class="less-than">
         <p></p>
         <p></p>
     </div>
   </div>
  </div>
</template>

<script>
export default {
  name: 'Calendar',
  data: function() {
    return {
        active: false,
        days: ['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa'],
        monthDays: {
            july: ['1', '2', '3', '4', '5', '6','7',
            '8', '9', '10', '11', '12', '13','14','15', '16', '17', '18', '19', '20','21',
            '22', '23', '24', '25', '26', '27', '28', '29', '30', '31'
            ],
            august: ['1', '2', '3', '4', '5', '6','7',
            '8', '9', '10', '11', '12', '13','14','15', '16', '17', '18', '19', '20','21',
            '22', '23', '24', '25', '26', '27', '28', '29', '30', '31'
            ],
            september: ['1', '2', '3', '4', '5', '6','7',
            '8', '9', '10', '11', '12', '13','14','15', '16', '17', '18', '19', '20','21',
            '22', '23', '24', '25', '26', '27', '28', '29', '30'
            ]
        }
    }
  },
  methods: {
      disabled: function(index) {
          document.getElementById(`disabled${index}`).classList.toggle('active');
      }
  }
}
</script>

<style>
#calendar {
position: absolute;
background: #fefbf3;
top: 83%;
width: 100vw;
height: 80%;
display: flex;
flex-direction: row;
z-index: -1;
}
.calendar-container {
position: absolute;
border: 1px solid #c4c3bf;
width: 350px;
top: 30%;
background-color: #fff;
height: 330px;
border-radius: 4px;
}
.july {
left: 290px
}
.august {
left: 0;
right: 0;
margin: 0 auto;
}
#augustDay:hover{
background-color: #fff;
opacity: 0;
}

.september {
right: 290px;
}
.calendar-header {
margin-top: 20px;
 text-align: center;
 color: #4d4d4d;
 font-weight: 600;
 margin-bottom: 5px;
}
.date {
margin-top: 20px;
padding: 20px;
display: grid;
grid-template-columns: repeat(auto-fit, minmax(40px, 1fr));
}
.day_name, .days {
font-size: 12px;
text-align: center;
color: #6b6a6a;
}
.day_name {
margin-bottom: 26px;
margin-top: -10px;
font-weight: 500;
}
.days {
margin-bottom: 20px;
width: 20px;
height: 18px;
margin-left: 10px;
text-align: center;
border-radius: 50px;
cursor: pointer;
}
.days:hover {
color: #fff;
background: #ffb505;
}
.active {
background: #cbcbcb;
}
.active:hover {
 background: #cbcbcb; 
}
.calendar-navigation {
display: flex;
flex-direction: row;
position: absolute;
top: 75%;
left: 47%;
cursor: pointer;
}
.greater-than > p, .less-than > p {
width: 3px;
height: 20px;
background: #4d4d4d;
}
.greater-than > p {
margin-right: 15px;
}
.greater-than > p:first-child {
transform: rotate(45deg);
margin-bottom: -8px;
}
.greater-than > p:nth-child(2) {
transform: rotate(-45deg);
margin-top: -5px;
}
.inner-circle {
width: 25px;
height: 25px;
border-radius: 50px;
background: #4d4d4d;
margin-left: 15px;
margin-right: 15px;
margin-top: 20px;
}

.less-than > p {
margin-left: 15px;
}  
.less-than > p:first-child {
transform: rotate(-45deg);
margin-bottom: -8px;
}
.less-than > p:nth-child(2) {
transform: rotate(45deg);
margin-top: -5px;
}
</style>
