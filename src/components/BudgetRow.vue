<template>
  <!-- EDIT CODE BELOW -->
  <v-row>
    <v-col cols="2">
      <v-btn @click="removeRow" icon small dark color="primary">
        <v-icon> mdi-minus-circle </v-icon>
      </v-btn>
    </v-col>

    <v-col cols="5">
      <v-select
        v-model="budgetType"
        label="Budget Type"
        :items="budgetTypes"
        :item-text="(item) => item.name"
        @change="loadValue"
        return-object
      />
    </v-col>

    <v-col cols="5">
      <v-text-field
        v-model="amount"
        @change="loadValue"
        class="currency-input"
        label="Enter amount"
        type="number"
        prefix="$"
      />
    </v-col>
  </v-row>
</template>

<script>
import { loadBudgetTypes } from "@/mock.js";

export default {
  name: "BudgetRow",
  props: ["value", "data", "index"],
  data() {
    return {
      budgetType: null,
      budgetTypes: [],
      amount: 0,
    };
  },
  created() {
    this.budgetTypes = loadBudgetTypes();
  },
  methods: {
    loadValue(value) {
      if (isNaN(value)) {
        return;
      }
      this.$emit("input", value);
    },
    removeRow() {
      this.$emit("remove", this.index);
    },
  },
};
</script>

<style>
.col-2 {
  align-items: center;
  justify-content: center;
  display: flex;
}
</style>