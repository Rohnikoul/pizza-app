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
          </div>
        </div>
        <status />
        <hr class="separator" />
        <div class="customerSection">
          <span class="nameLabel">{{ nameLabel }}</span>
          <span class="customerName"> {{ order.customerName }} </span>
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
      nameLabel: "Customer Name",
      ordersList: [
        {
          orderId: 101,
          customerName: "Rohni",
          itemCount: "2",
          orderName: "Margherita",
          amount: 550,
          image: require("./images/marghrita.jpg"),
        },
        {
          orderId: 102,
          customerName: "Roshini",
          itemCount: "3",
          orderName: "Cheese n Corn",
          amount: 700,
          image: require("./images/cheeseCorn.jpg"),
        },
        {
          orderId: 103,
          customerName: "Rohini",
          itemCount: "1",
          orderName: "Pepper Barbecue Chicken",
          amount: 200,
          image: require("./images/farmhouse.jpg"),
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
  width: 71%;
}

.customerSection {
  width: 40%;
}

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

.nameLabel {
  font-size: 20px;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  color: #0066a7;
}

.customerName {
  float: right;
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
  color: #333333;
}
</style>
