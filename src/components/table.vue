<template>
  <div class="table-responsive">
    <table class="table" style="font-size:14px">
      <thead>
        <tr>
          <th scope="col">Products</th>
          <th scope="col">Order ID</th>
          <th scope="col">Date</th>
          <th scope="col">Customer Name</th>
          <th scope="col">Status</th>
          <th scope="col">Amount</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(product, i) in products" :key="i">
            <td>
                <img src="../assets/bag.png" alt="Avatar" class="portfolio-img me-2" style="width:40px; height:40px">
                {{product.product}}</td>
            <td>{{product.productId}}</td>
            <td>{{product.date}}</td>
            <td>{{product.name}}</td>
            <td>{{product.status}}</td>
            <td>{{product.amount}}</td>
            <td>
                <a href="#" class="text-decoration text-dark mx-auto"><i class="bi bi-three-dots "></i></a>
            </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
    data() {
        return {
            products:[
                {
                    product:'Iphone 13 Pro',
                    productId:'#1235',
                    date:'Jun 29 2022',
                    name:'Anastasia Hasuna',
                    status:'Delivered',
                    amount:'$1100.00',
                },
                {
                    product:'Macbook pro',
                    productId:'#1635',
                    date:'Jun 28 2022',
                    name:'Nasuha Makusta',
                    status:'Pending',
                    amount:'$1200.00',
                },
                {
                    product:'Apple Watch',
                    productId:'#1565',
                    date:'Jun 27 2022',
                    name:'Induan Kastorika',
                    status:'Canceled',
                    amount:'$400.00',
                },
                {
                    product:'Apple Pen',
                    productId:'#1525',
                    date:'Jun 26 2022',
                    name:'Pogba Nehuntas',
                    status:'Delivered',
                    amount:'$200.00',
                }


            ]
        }
    },
};
</script>
<style scoped>
.portfolio-img {
  border-radius: 50%;
  object-fit: cover;
}
</style>