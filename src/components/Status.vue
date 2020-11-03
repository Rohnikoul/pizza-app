<template >
  <div>
    <div class="progress__actions">
      <div class="title">
        Current Status:
        {{ currentStep.label }}
      </div>
      <div class="btn" v-on:click="nextStep">Change Order Status</div>
    </div>
  </div>
</template>


<script>
export default {
  name: "Menu",
  data() {
    return {
    currentStep: 'Delivered',
      steps: [
        { label: "Order Received" },
        { label: "Baking Pizza" },
        { label: "Out for delivery" },
        { label: "Delivered" },
      ],
    };
  },
  props: {
  },

  methods: {
    nextStep() {
        console.log(this.steps[0].label);
      const steps = this.steps;
      const currentStep = this.currentStep;
      const currentIndex = steps.indexOf(currentStep);

      if (steps[currentIndex + 1]) {
        return (this.currentStep = steps[currentIndex + 1]);
      }

    },
  },
};
</script>

<style scoped>
.btn {
  width: fit-content;
  padding: 10px 18px;
  border-radius: 26px;
  cursor: pointer;
  user-select: none;
  background: rgb(0, 102, 167);
  color: white;
  font-weight: bold;
  text-transform: uppercase;
  float:right;
}

.progress__actions {
}

.title {
  font-size: 20px;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  color: rgb(101, 171, 11);; 
}
</style>
