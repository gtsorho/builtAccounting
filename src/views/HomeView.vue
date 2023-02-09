<template>
   <Sidebar :sidebarVal="sidebarbool"  @humburgerClick="sidebarbool = true"  @currentTab="(data) => currentTab = data"/>
    <div id="main">
      <Navbar :sidebarbool="sidebarbool" @changestate="sidebarbool = !sidebarbool"/>
      <div class="row row-cols-1 row-cols-md-3 row-cols-md-3 pt-2 g-4">
        <div class="col" v-for="(cardx , i) in uppercards" :key="i">
          <Card   :card="cardx"/>
        </div>
      </div>
      <div class="row">
        <div class="col-sm-8 mb-3 mb-sm-0">
          <div class="card bg-transparent">
            <div class="card-body">
              <div class="d-flex card-title">
                <div class="p-2 flex-grow-1 fw-bold">Total Revenue</div>
                <div class="p-2 " style="font-size:12px">Data Updates Every 3 Hrs
                  <button class=" btn btn-secondary btn-sm"  style="font-size:12px"> View All Orders</button>
                </div>
              </div>
              <div style="height:200px">
                <Bar/>
              </div>
            </div>
          </div>
        </div>
        <div class="col-sm-4">
          <div class="card bg-transparent">
            <div class="card-body">
              <div class="d-flex card-title">
                <div class="p-2 flex-grow-1 fw-bold">Most Sold Items</div>
                <div class="p-2 " style="font-size:12px">
                  <button class=" btn btn-outline-light text-dark btn-sm fw-bolder" ><i class="bi bi-three-dots"></i></button>
                </div>
              </div>
              <div>
                <Pie/>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="card mt-3">
        <div class="card-body">
          <div class="d-flex card-title">
            <div class="p-2 flex-grow-1 fw-bold">Total Revenue</div>
            <div class="p-2 " style="font-size:12px">Data Updates Every 3 Hrs
              <button class=" btn btn-secondary btn-sm"  style="font-size:12px"> View All Orders</button>
            </div>
          </div>
          <Table/>
        </div>
      </div>
    </div>
</template>
<script>


import Sidebar from '../components/sidebar.vue'
import Navbar from '../components/navbar.vue'
import Card from '../components/card.vue'
import Bar from '../components/barchart.vue'
import Pie from '../components/pie.vue'
import Table from '../components/table.vue'

export default {
  components: { 
    Bar,
    Sidebar,
    Navbar,
    Card,
    Pie,
    Table
  },
    data() {
        return {
            notifications:[],
            currentTab:'ExtentionsTab',
            sidebarbool:true,
            username:'',
            uppercards:[
              {
                title:'Todays Sales',
                amount:'$20.4',
                percentage:75,
                comment:'We have sold 123 Items',
                color:'#174cfe'
              },
              {
                title:'Todays Revenue',
                amount:'$8.2K',
                percentage:80,
                comment:'Available to payout',
                color:'#02802e'
              },
              {
                title:'In Escrow',
                amount:'$18.2K',
                percentage:60,
                comment:'Available to payout',
                color:'#a00404'
              }
            ]
        }
    },
}
</script>
<style scoped>
    .btn-secondary{
      background-color:  #e4e4e4;
      border:none;
      color: #000;
      }
    .bi{
      padding-inline: 1px;
    }
    body{
            min-height: 100vh;
        min-height: -webkit-fill-available;
        background-color: rgb(230, 230, 230) !important;
    }
    .dropdown-item{
        font-size: 12px;
    }
    .btn-light:focus{
    color: #000;
    background-color: #fbf9f9;
    border-color: #f9fafb;
    box-shadow: 0 0 0 0.25rem rgb(13 110 253 / 0%) !important;
    }
    #main {
        transition: margin-left .5s;
        padding: 16px;
        margin-left: 250px;
    }
</style>