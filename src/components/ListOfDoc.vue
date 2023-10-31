<template>
    <ApplicationNavigationBar />
    <main class="main-container">
      <section class="description">
        <h2 class="title">Document Request</h2>
        <p class="content">List of Documents Available for Request</p>
        <table class="table">
          <thead>
            <tr>
              <th>ID</th>
              <th>Document Type</th>
              <th>Fee</th>
              <th>Quantity</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="category in categories" :key="category.id">
              <td>{{ category.id }}</td>
              <td>{{ category.docType }}</td>
              <td>{{ category.description }}</td>
              <td>
                <div class="input-group w-auto align-items-center">
                  <input
                    type="button"
                    value="-"
                    class="button-minus border rounded-circle icon-shape icon-sm mx-1"
                    @click="decreaseQuantity(category)"
                  />
                  <input
                    type="number"
                    :value="category.quantity"
                    step="1"
                    max="10"
                    name="quantity"
                    class="quantity-field border-0 text-center w-25"
                    @input="updateQuantity(category, $event.target.value)"
                  />
                  <input
                    type="button"
                    value="+"
                    class="button-plus border rounded-circle icon-shape icon-sm"
                    @click="increaseQuantity(category)"
                  />
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </section>
    </main>
    <Footer />
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import ApplicationNavigationBar from './ApplicationNavigationBar.vue';
import Footer from './Footer.vue';
  
  const categories = ref([
    { id: 1, docType: "Authentication", description: "30.00 / PAGE", quantity: 1 },
    { id: 2, docType: "CAV or Certification, Authentication, Verification (Local/DFA)", description: "370.00 / SET", quantity: 1 },
  ]);
  
  const decreaseQuantity = (category) => {
    if (category.quantity > 1) {
      category.quantity--;
    }
  };
  
  const increaseQuantity = (category) => {
    if (category.quantity < 10) {
      category.quantity++;
    }
  };
  
  const updateQuantity = (category, value) => {
    const intValue = parseInt(value, 10);
    if (!isNaN(intValue) && intValue >= 1 && intValue <= 10) {
      category.quantity = intValue;
    }
  };
  </script>

<style scoped>
icon-shape {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    vertical-align: middle;
}

.icon-sm {
    width: 50px;
    height: 50px;
    
}
.table {
    color: #000;
    align-self: start;
    max-width: 960px;
    margin: 28px 0 0 20px;
    font: 700 25px Saira Condensed, sans-serif;
  }
.content {
    color: #000;
    align-self: start;
    max-width: 960px;
    margin: 28px 0 0 20px;
    font: 700 25px Saira Condensed, sans-serif;
  }
.title {
    color: #000;
    text-align: left;
    align-self: stretch;
    font: 700 30px Saira Condensed, sans-serif;
  }
 .main-container {
    background: linear-gradient(127.55deg, #f6557e, rgba(255, 201, 245, 0.949));
    display: flex;
    flex-direction: column;
  }
  .description {
    background-color: #fff;
    align-self: center;
    display: flex;
    margin-top: 39px;
    margin-bottom: 39px;
    width: 80%;
    max-width: 1117px;
    flex-direction: column;
    border-radius: 10px;
    padding: 5%;
    
  }

  @media (max-width: 991px) {
    .description {
      max-width: 100%;
    }
  }
</style>