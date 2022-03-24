<template>
  <h1>BANK</h1>
  <div>INCOME: {{ income }}€</div>
  <div>OUTCOME: {{ outcome }}€</div>
  <div>BALANCE: {{ balance }}€</div>
  <input
    type="text"
    class="border rounded-md"
    v-model="name"
    placeholder="Name..."
  />
  <input
    type="number"
    class="border rounded-md ml-6"
    v-model="amount"
    placeholder="Amount ...€"
  />
  <button
    class="bg-teal-500 text-white border rounded-md px-2 ml-3"
    @click="addItem"
  >
    add
  </button>
  <ul>
    <li v-for="(item, i) in items" :key="i">
      {{ item.name }}: {{ item.amount }} €
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      amount: 0,
      items: [],
    };
  },
  computed: {
    income() {
      return this.items
        .filter((item) => item.amount > 0)
        .reduce((acc, item) => acc + item.amount, 0);
    },
    outcome() {
      return this.items
        .filter((item) => item.amount < 0)
        .reduce((acc, item) => acc + item.amount, 0);
    },

    balance() {
      return this.income + this.outcome;
    },
  },

  methods: {
    addItem() {
      this.items.push({
        name: this.name,
        amount: this.amount,
      });
    },
  },
};
</script>
