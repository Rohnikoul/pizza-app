<template>
  <div>
    <div v-for="order in ordersList" :key="order.orderId">
      <div class="container">
        <div class="content">
          <img class="image" :src="order.image" alt="error_while_loading" />
          <div class="orderDetails">
            <span class="orderName"> {{ order.orderName }} </span>
            <span class="itemCount"> {{ order.itemCount }} </span>
            <span class="amount"> ₹{{ order.amount }} </span>
            <div class="orderDescription">{{ order.orderDescription }}</div>
          </div>
          <div class="vl"></div>
          <div class="customerSection">
          <span class="nameLabel">{{ nameLabel }}</span>
          <span class="customerName"> {{ order.customerName }} </span>
          <status />
        </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import Status from "./Status.vue";

export default {
  name: "Menu",
  components: {
      Status,
  },
  data() {
    return {
      nameLabel: "Customer Name : ",
      ordersList: [
        {
          orderId: 101,
          customerName: "Rohni",
          itemCount: "2",
          orderName: "Margherita",
          orderDescription:
            "A classic delight with 100% Real mozzarella cheese !",
          amount: 550,
          image: require("./images/marghrita.jpg"),
        },
        {
          orderId: 102,
          customerName: "Roshini",
          itemCount: "3",
          orderName: "Cheese n Corn",
          orderDescription:
            "Sweet & Juicy Golden corn and 100% real mozzarella cheese in a delectable combination !",
          amount: 700,
          image: require("./images/farmhouse.jpg"),
        },
        {
          orderId: 103,
          customerName: "Rohini",
          itemCount: "1",
          orderName: "Farm House",
          orderDescription:
            "Delightful combination of onion, capsicum, tomato & grilled mushroom !",
          amount: 200,
          image: require("./images/cheeseCorn.jpg"),
        },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  background-color: #ffffff;
  border: 2px solid #333333;
  border-radius: 5px;
  margin: 10px 20px;
}

.content {
  display: flex;
  flex-direction: row;
}

.image {
  margin-left: 30px;
  border: 1px solid #dddddd;
  border-radius: 4px;
  padding: 5px;
  width: 126px;
}

.orderDetails {
  font-size: 20px;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  margin: 30px 0 0 40px;
  width: 50%;
}

/* .customerSection {
  width: 40%;
} */

.orderName {
  padding-right: 30px;
  float: left;
}
.amount {
  color: #0066a7;
  float: right;
}

hr.separator {
  border-top: 3px dashed #bbbbbb;
  width: 72%;
}

.nameLabel, .customerName{
  font-size: 15px;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  color: #0066a7;
}

.customerName {
  color: #333333;
}
.orderDescription {
  display: flex;
  font-size: 15px;
  font-weight: normal;
  font-style: oblique;
  margin-top: 15px;
}
.vl {
  margin: 0 25px;
  border-left: 5px solid #0066a7;
  height: 140px;
}
</style>
