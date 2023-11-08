<template>

<div class="root">
<div class="info">
        <div class="supplierInfo">
        <p class="title">Supplier information</p>
        <figcaption>
            <img src="../assets/img/photo.jpg" alt="Drivers Photot" height="100" width="100">
            <br>
            {{ name }}
            <br>
            {{ rating }}
        </figcaption>
    </div>
    <br>
    <div class="knownLang">
        <label>Add Languages</label>
        <br>
        <img src="../assets/img/flag1.jpeg" alt="" width="30" height="30"> 
        <img src="../assets/img/flag2.jpeg" alt="" width="30" height="30">
        <img src="../assets/img/flag3.jpeg" alt="" width="30" height="30">
        <img src="../assets/img/flag4.jpeg" alt="" width="30" height="30">
    </div>
</div>
<div class="information">
    <label>Driver</label>
    <p> {{ fullName }}</p>
    <label>Name of the carrier</label>
    <p> {{ carrier }}</p>
    <label>National Registration Number / Transport Name</label>
    <p> {{ regNumber }}</p>
    <p>{{  transName }}</p>
</div>
<div class="autoInfo">
    <div class="time">
        <div>
            <img src="../assets/img/calendar.jpeg" height="20" width="20">
            <span>{{ date }}</span>
        </div>
        <div>
            <img src="../assets/img/time.jpeg" alt="Time Logo" height="20" width="20">
            <span>{{ time }}</span>
        </div>
    </div>
    <img src="" alt="">
    <div class="infoBar">
        <img src="../assets/img/car.jpeg" alt="Car Image" width="150" height="100">
        <div>
        <p>Car Registration</p>
        <p>{{ carNumber }}</p>
        <p>{{ model }}, Color: {{ color }}</p>
        <button class="invoice"><img src="../assets/img/document-logo.webp" alt="Document Logo">Invoice</button>
        </div>
    </div>
</div>
</div>
</template>
<script>


 export default {
    name: 'AppSupInfo',

    data() {
        return{
            name: 'Adam',
            rating: 4.5,
            fullName: 'Adam Lopoto',
            carrier: 'BAMBAM SIA',
            regNumber: '"Miranda"',
            transName: '',
            date: '18.feb',
            time: '11:00',
            carNumber: 'HZ - 7221',
            model: 'Skoda Fabia',
            color: 'Silver'
        }
    }
 }
</script>
<style scoped>

.root {
    position: static;
    display: flex;
    flex-direction: column;
}
.title{
    text-align: left;
    }
.invoice {
    position: relative;
    margin-left: 200px;

}

.invoice img {
    width: 20px;
    height: 20px;
    transform: translate(50%, 50%);
}
 p{
    color: black;
    text-align: left;
    margin-top: 0;
   
 }

.info {
    display: flex;
    flex-direction: row;
    
}

 .supplierInfo img {
    position: relative;
    border-radius: 20px;
    
 }
 
 .time {
    display: flex;
    flex-direction: row;
    border-bottom: solid 1px grey;
 }

 .knownLang {
    position: relative;
    float: right;
    margin: 30px 0 0 100px;
    
 }

 .knownLang img {
    display: inline;
 }

 .information {
    margin-top: 30px;
 }

 .autoInfo {
    position: static;
    background-color: rgb(197, 191, 191);
    width: 100%;
    margin-right: 0 !important;
 }

 .infoBar {
    display: flex;
    flex-direction: row;
 }

 .infoBar img {
    margin: 10px;
    border-radius: 10px;
 }

 figcaption {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    
    left: 10px;
 }

 label {
    color: grey;
 }
</style>