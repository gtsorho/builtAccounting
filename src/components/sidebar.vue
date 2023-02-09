<template>
  <div id="mySidenav" class="sidenav px-3" >
  <span style="font-size:20px;cursor:pointer"  class="text-secondary humburger text-center me-2"  v-show="!sidebarbool" @click="sidebarbool = !sidebarbool; $emit('humburgerClick') ">&#9776;</span>
    <span class="text-start" v-show="sidebarbool">
        <img  style="width:60%;" class="ms-0" src="../assets/logo1.png" > 
      <hr class=" mx-2" style="border: 1.55px solid rgb(120 120 120)">  
      <a href="#" class="btn my-2" @click="activeBtn = 'Dashboard'" :class="{active: activeBtn === 'Dashboard' }" ><i class="bi bi-columns-gap me-1" ></i>Dashboard</a>
      <a href="#" class="btn my-2"  @click="activeBtn = 'Statistics'" :class="{active: activeBtn === 'Statistics' }"><i class="bi bi-bar-chart-fill me-1" ></i>Statistics</a>
      <a href="#" class="btn my-2"  @click="activeBtn = 'Payments'" :class="{active: activeBtn === 'Payments' }" ><i class="bi bi-credit-card me-1"></i>Payments</a>
      <a href="#" class="btn my-2"  @click="activeBtn = 'Transaction'" :class="{active: activeBtn === 'Transaction' }"><i class="bi bi-arrows-angle-contract me-1" ></i>Transaction</a>
      <a href="#" class="btn my-2" @click="activeBtn = 'Products'" :class="{active: activeBtn === 'Products' }" ><i class="bi bi-bag-check me-1" ></i>Products</a>
      <a href="#" class="btn my-2" @click="activeBtn = 'Customer'" :class="{active: activeBtn === 'Customer' }" ><i class="bi bi-bag-check me-1" ></i>Customer</a>
      <a href="#" class="btn my-2"  @click="activeBtn = 'Messages'" :class="{active: activeBtn === 'Messages' }"><i class="bi bi-chat-left-text me-1" ></i>Messages</a>
    </span>
</div>
</template>
<script>
export default {
    name:'sidebar',
    props:[
      'sidebarVal'
    ],
    emits: [
      'humburgerClick',
      'currentTab'
      ],
    data() {
      return {  
        activeBtn:'Dashboard',
        sidebarbool:this.sidebarVal
      }
    },
    mounted(){
      var w = window.innerWidth;
      if(w < 750){
        this.sidebarbool = false
        document.getElementById("mySidenav").style.width = "50px";
        document.getElementById("main").style.marginLeft= "50px";           
      }else{
        this.sidebarbool = true
        document.getElementById("mySidenav").style.width = "250px";
        document.getElementById("main").style.marginLeft = "250px"; 
      }
    },
    watch:{
      sidebarVal(newVal){
        console.log(newVal)
        if(newVal){
          this.sidebarbool = true
            document.getElementById("mySidenav").style.width = "250px";
            document.getElementById("main").style.marginLeft = "250px";            
        }else{
          this.sidebarbool = false
            document.getElementById("mySidenav").style.width = "50px";
            document.getElementById("main").style.marginLeft= "50px";
        }
      }
    },
    methods: {
       
    },
}
</script>
<style scoped>

 /* card style */
    /* margin: 10px; */
    /* width: 80.5% !important;*********************** */
    /* height: 90%; */
    /* position: fixed !important;***************** */
    /* z-index: 1;
    overflow-x: hidden;
    transition: 0.5s;
    padding-top: 10px; */

.humburger:hover{
  color: #d5d5d5 !important;
}
.accordion-button:focus {
    z-index: 3;
    border-color: rgba(7, 7, 7, 0) !important;
    outline: 0;
  box-shadow: 0 0 0 0.25rem rgb(13 110 253 / 0%) !important;
}
#flush-collapseOne a {
  padding-left: 20% !important;
  text-decoration: none;
  font-size: 13px !important;
  color: #818181;
  display: block;
  transition: 0.3s;

}
 #flush-collapseOne a:hover {
  color: #f1f1f1;
}

.sidenav {
  height: 100%;
  width: 250px;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  /* background-image: linear-gradient(198deg, #000000, #c2213d) !important; */
  border-right: 3px solid rgb(201, 201, 201);
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 10px;
}

.sidenav a {
  /* padding: 8px 8px 8px 32px;  */
  text-decoration: none;
  font-size: 15px;
  /* background-color: transparent !important; */
  color: #818181;
  display: block;
  text-align: left !important;
  transition: 0.3s;
}

.sidenav a:hover {
  color: #ffffff;
  background-color: #174cfe !important;
 box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

.active {
  background-color: #174cfe !important;
  color: #fff !important;
  border: 0px;
 box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);

}

.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}

@media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
}
</style>