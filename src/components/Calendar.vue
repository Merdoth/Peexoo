<template>
  <div id="calendar">
   <div class="calendar-container july">
          <div class="calendar-header">
          <span class="calendar-month">{{ month[currentDate.month ] +' '+ currentDate.year}}</span>
      </div>
        <div class="date">
              <div class="day_name" v-for="(day, index) in days" :key="index">
              {{day}}
          </div>
             <div id="augustDay" v-for="(n, index) in (firstMonthDay -1)" :key="'prev'+index">
          {{ (prevMonthDays +1) - firstMonthDay + n }}
        </div>
          <div 
          @click="disabled($event)" 
          :class="{ active: monthDay === currentDate.date}"
          class="days" v-for="(monthDay, index) in currentMonthDays" 
          :key="index">
              {{monthDay}}
          </div>
      </div>
   </div>
   <!-- <div class="calendar-container august">
      <div class="calendar-header">
          <span class="calendar-month">{{ month[currentDate.month + 1]}}</span>
      </div>
      <div class="date">
              <div class="day_name" v-for="(day, index) in days" :key="index">
              {{day}}
          </div>
             <div id="augustDay" v-for="(n, index) in (firstMonthDay -1)" :key="'prev'+index">
          {{ (prevMonthDays +1) - firstMonthDay + n }}
        </div>
          <div 
          @click="disabled($event)" 
          :class="{ active: monthDay === currentDate.date}"
          class="days" v-for="(monthDay, index) in currentMonthDays" 
          :key="index">
              {{monthDay}}
          </div>
      </div>
   </div>
   <div class="calendar-container september">
      <div class="calendar-header">
          <span class="calendar-month">{{ month[currentDate.month + 1]}}</span>
      </div>
        <div class="date">
              <div class="day_name" v-for="(day, index) in days" :key="index">
              {{day}}
          </div>
             <div id="augustDay" v-for="(n, index) in (firstMonthDay -1)" :key="'prev'+index">
          {{ (prevMonthDays +1) - firstMonthDay + n }}
        </div>
          <div 
          @click="disabled($event)" 
          :class="{ active: monthDay === currentDate.date}"
          class="days" v-for="(monthDay, index) in currentMonthDays" 
          :key="index">
              {{monthDay}}
          </div>
      </div>
   </div> -->
   <div class="calendar-navigation">
     <div class="greater-than" @click="dateRight()" >
        <p></p>
        <p></p>
     </div> 
     <div class="inner-circle"></div>
     <div class="less-than" @click="dateLeft()">
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
        limit: 3,
        days: ['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa'],
        month: [
          'January','February','March','April','May','June','July',
          'August','September','October','November','December'
        ],
        currentDate: {
          date: 0,
          month: 0,
          year: 0
        }
    }
  },
   computed: {
      prevMonthDays() {
        let year = this.currentDate.month === 0 ? this.currentDate.year - 1 : this.currentDate.year;
        let month = this.currentDate.month === 0 ? 12 : this.currentDate.month;
        return new Date(year, month, 0).getDate();
      },
      firstMonthDay() {
        let firstDay = new Date(this.currentDate.year, this.currentDate.month, 1).getDay();
        if(firstDay === 0) firstDay = 7;
        return firstDay;
      },
      currentMonthDays() {
        return new Date(this.currentDate.year, this.currentDate.month +1, 0).getDate();
      }
    },
  methods: {
      disabled: function(event) {
          event.target.classList.toggle('disabled');
      },
      getCurrentDate() {
        let today = new Date();
        this.currentDate.date = today.getDate();
        this.currentDate.month = today.getMonth();
        this.currentDate.year = today.getFullYear();
      },
      dateLeft() {
        if(this.currentDate.date === this.currentMonthDays) {
          this.currentDate.date = 1;
          this.monthUp();
        }
        else {
          this.currentDate.date += 1;
        }
      },
      dateRight() {
        if(this.currentDate.date === 1) {
          this.currentDate.date = this.prevMonthDays;
          this.monthDown();
        }
        else {
          this.currentDate.date -= 1;
        }
      },
      monthUp() {
        if(this.currentDate.month === 11) {
          this.currentDate.month = 0;
          this.currentDate.year += 1;
        }
        else {
          this.currentDate.month += 1;
        }        
      },
      monthDown() {
        if(this.currentDate.month === 0) {
          this.currentDate.month = 11;
          this.currentDate.year -= 1;
        }
        else {
          this.currentDate.month -= 1;
        } 
      }
  },
  created() {
      this.getCurrentDate();
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
#augustDay{
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
margin-bottom: 15px;
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
background: #ffb505;
color: #fff;
}
.disabled {
background: #cbcbcb;
color: #cbcbcb;
}
.disabled:hover {
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
