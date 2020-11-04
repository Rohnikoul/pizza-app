<template >
  <div>
    <div class="stepLabel">
      {{ stepLabel }}
      {{ currentStep.label }}
    </div>
    <!-- ToDo: Add stepper instead of Button -->
    <div class="statusButton" v-on:click="nextStep">
      {{ changeStatusLabel }}
    </div>
  </div>
</template>


<script>
export default {
  name: "Menu",
  data() {
    return {
      stepLabel: "Current Status:",
      changeStatusLabel: "Change Order Status",
      currentStep: "",
      steps: [
        { label: "Order Received" },
        { label: "Baking Pizza" },
        { label: "Out for delivery" },
        { label: "Delivered" },
      ],
    };
  },
  methods: {
    nextStep() {
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
.statusButton {
  width: fit-content;
  padding: 10px 18px;
  border-radius: 26px;
  cursor: pointer;
  user-select: none;
  background: #0066a7;
  color: #ffffff;
  font-weight: bold;
  text-transform: uppercase;
  float: right;
}

.stepLabel {
  font-size: 20px;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
  color: #65ab0b;
}
</style>
