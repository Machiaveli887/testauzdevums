<template>
    <div class="root">
    <div>
        <p><strong>Overview</strong></p>
        <p>{{ startDate }} - {{ endDate }} <span class="greyItem">({{ tourTime }})</span></p>
        
    
    </div>
    <div>
        <div class="container">
        <img src="../assets/img/passanger.jpeg" alt="Passanger Info" width="20" height="20">
        <p>{{ numberOfPassangers }} Passangers <span class="greyItem">({{ numberOfAdults }} Adults)</span></p>
        <p></p>
        </div>

        <div class="container">
            <img src="../assets/img/suitcase.jpeg" alt="Suitcase Image" width="20" height="20">
            <p>{{ lSuitCase }} Large Suitcases</p>
        </div>

        <div class="dayInfo">
            <button @click="firstDate">
                <img src="../assets/img/calendar.jpeg">
                {{ todayDate }}
            </button>
            <button @click="secondDate">
                <img src="../assets/img/calendar.jpeg">
                {{ tommorowDate }}
            </button>
                <button @click="thirdDate">
                    <img src="../assets/img/calendar.jpeg" alt="Calendar Icon">
                    <span>
                        {{ twoDaysLater }}
                    </span>
                </button>
            </div>

            <div v-if="firstDayVisible" class="toolbar">
                <div>
                    {{ time }}
                </div>
                <div>
                    
                    <label class="custom-checkbox">
                   <input type="checkbox">
                    <span class="checkmark"></span>
                    <img src="../assets/img/loc.jpeg" alt="Location Logo" width="20" height="20">
                </label>
                </div>
                <div>
                    <p>Hamburg Airport, Flughafenstraße, <br> Hamburg, Germany</p>
                    <p>Ibis Hamburg St Pauli Messe, Simon-von-<br>Utrecht-Straße 63, 20359 Hamburg,<br> Germany</p>
                </div>
            </div>
        
    </div>
    <div>
        <label for="">
            <img src="" alt="">
            {{ routeLength }}km
        </label>
        <label for="">
            <img src="" alt="">
            {{ routeTime }} Hours
        </label>
        <div class="add-info">
            <p>Additional information</p>
            <div class="notes">
                <img src="../assets/img/attention.png" alt="Attention Logo">

                <ul v-for="note in notes" :key="note.id" :value="note.info">
                    
                    <li>{{ note.info }}</li>
                </ul>
            </div>
        </div>
    </div>
</div>
</template>
<script>
 export default {
    name: 'over-view',
    data(){
        return{
            firstDayVisible: false,
            secondDayVisible: false,
            thirdDayVisible: false,
            time: '11:00',
            startDate: '7 March 2023',
            endDate: '9 march 2023' ,
            numberOfPassangers: 7 ,
            numberOfAdults: 5 ,
            lSuitCase: 3 ,
            todayDate: '7 March' ,
            tommorowDate: '8 March' ,
            twoDaysLater: '9 March' ,
            routeLength: 124.27 ,
            routeTime: '2:10',
            notes: [
                { id:1, info:'Need 2 Kid Seats'},
            ]

        } 
    },
    computed: {
    tourTime() {
        const days = this.countDays(this.startDate, this.endDate);
        return `${days} Days`;
    },
    },
    
    methods: {
        

        countDays(startDate, endDate) {
            const start = new Date(startDate);
            const end = new Date(endDate);

            const timeDiff = end - start;

            const days = Math.floor(timeDiff / (1000 * 60 * 60 * 24));

            return days;
        },

        firstDate(){
            this.firstDayVisible = true;
            this.secondDayVisible = false;
            this.thirdDayVisible = false;
            
        },
        secondDate(){
            this.firstDayVisible = false;
            this.secondDayVisible = true;
            this.thirdDayVisible = false;
        },
        thirdDate(){
            this.firstDayVisible = false;
            this.secondDayVisible = false;
            this.thirdDayVisible = true;
        }
     },
     };
</script>
<style scoped>
.root {
    padding: 10px;
    display: flex;
    flex-direction: column;
    border-left: solid 1px grey;
    
}

.toolbar {
    display: flex;
    flex-direction: column;
}
.custom-checkbox {
  position: relative;
  padding-left: 30px;
  cursor: pointer;
}

.custom-checkbox input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

.checkmark {
  position: absolute;
  top: 0;
  left: 40px;
  height: 20px;
  width: 20px;
  border: 2px solid #333;
  border-radius: 50%;
}

.custom-checkbox input:checked + .checkmark {
  background-color: #333;
}

.custom-checkbox .checkmark::after {
  content: "";
  position: absolute;
  display: none;
}

.custom-checkbox input:checked + .checkmark::after {
  display: block;
  left: 7px;
  top: 5px;
  width: 4px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}

.custom-checkbox img {
    position: absolute;
    right: 30px;
}

.dayInfo button{
    font-size: 16px;
}

.dayInfo img {
    height: 20px;
    width: 20px;
}



 .notes li{
    list-style: none;
 }

 .dayInfo {
    border-bottom: solid 1px grey;
    display: flex;
    flex-direction: row;
 }
.greyItem {
    color: grey;
 }

 .add-info p{
    text-align: left !important;
 }

 .notes {
    background-color: rgb(237, 212, 113);
    height: 160px;
    display: flex;
    flex-direction: column;

 }

 .notes li {
    position: relative;
    left: 90px;
    list-style:disc;
 }

 .notes img{
    position: relative;
    top: 27px;
    width: 50px;
    height: 50px;
    transform: translate(50%,50%);
 }

.container {
    display: flex;
    flex-direction: row;
}



 p {
    
    color: black;
    
 }
</style>