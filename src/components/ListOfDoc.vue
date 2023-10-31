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
              <td class="idnum">{{ category.id }}</td>
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
        <div class="div">
    <div class="div-2">
      <span
        style="
          font-family: Saira Condensed, Roboto, Helvetica,
            sans-serif;
          font-weight: 700;
          color: rgba(255, 0, 0, 1);
        "
        >VERY IMPORTANT: </span
      ><span
        style="
          font-family: Saira Condensed, Roboto, Helvetica,
            sans-serif;
          font-weight: 400;
          color: rgba(0, 0, 0, 1);
        "
        >Kindly upload your identification (ID) card for verification purposes.
        Any valid ID will do as long as it has your signature (e.g, Company ID,
        School ID, Alumni ID, government-issued IDs)</span
      >
    </div>
    <!--UPLOAD BUTTON-->
    <section class="hero is-light">
    <div class="hero-body">
      <div class="container has-text-centered">
        <p class="control uploader">
          <label for="imageInput" class="button is-dark is-fullwidth is-medium">
            <span class="icon is-small">
              <i class="fas fa-upload"></i>
            </span>
            <span>Upload image</span>
          </label>
          <input
            ref="imageInput"
            id="imageInput"
            type="file"
            accept="image/*"
            @change="handleImageUpload"
            class="is-sr-only"
          />
        </p>
      </div>
      <!-- Image preview -->
      <div class="field">
        <img id="thumbnail" :src="imageUrl" alt="image-preview-here" />
      </div>
    </div>
  </section>

    <div class="div-5">
      <span
        style="
          font-family: Saira Condensed, -apple-system, Roboto, Helvetica,
            sans-serif;
          font-weight: 700;
          color: rgba(255, 0, 0, 1);
        "
        >VERY IMPORTANT: </span
      ><span
        style="
          font-family: Saira Condensed, -apple-system, Roboto, Helvetica,
            sans-serif;
          font-weight: 400;
          color: rgba(0, 0, 0, 1);
        "
        ><br>In case you have been granted an Honorable Dismissal and COMPLIED,
        meaning you have been issued an Official Transcript of Records with
        Remarks &quot;Granted Transfer Credentials&quot; (Copy Good for that
        particular school you transferred in after leaving UIC), secure a Letter
        of No Objection from that school in order to process your request for
        Transcript of Records.<br /></span
      ><span
        style="
          font-family: Saira Condensed, -apple-system, Roboto, Helvetica,
            sans-serif;
          font-weight: 700;
          color: rgba(255, 0, 0, 1);
        "
        >VERY IMPORTANT: </span
      ><span
        style="
          font-family: Saira Condensed, -apple-system, Roboto, Helvetica,
            sans-serif;
          font-weight: 700;
          color: rgba(0, 0, 0, 1);
        "
        >Price is subject to change without prior notice.<br
      /></span>
    </div>
  </div>
      </section>
      <section class="navigation">
        <a href="/personalInfo2" type="button" class="btnBack">Back</a>
      
      <a href="/personalInfo2" type="button" class="btnNext">Next</a>
    </section>
    </main>
    <Footer />
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import ApplicationNavigationBar from './ApplicationNavigationBar.vue';
import Footer from './Footer.vue';
const imageUrl = ref('');

const handleImageUpload = (event) => {
  const file = event.target.files[0];
  if (file) {
    const reader = new FileReader();
    reader.onload = () => {
      imageUrl.value = reader.result;
    };
    reader.readAsDataURL(file);
  }
};
  const categories = ref([
    { id: 1, docType: "Authentication", description: "30.00 / PAGE", quantity: 1 },
    { id: 2, docType: "CAV or Certification, Authentication, Verification (Local/DFA)", description: "370.00 / SET", quantity: 1 },
    { id: 3, docType: "Certificate of English as Medium of Instruction", description: "60.00 / COPY", quantity: 1 },
    { id: 4, docType: "Certificate of Enrollment", description: "60.00 / COPY", quantity: 1 },
    { id: 5, docType: "Certificate of General Weighted Average (GWA)", description: "60.00 / COPY", quantity: 1 },
    { id: 6, docType: "Certificate of Government Recognition of the Program", description: "60.00 / COPY", quantity: 1 },
    { id: 7, docType: "Certificate of Grades", description: "60.00 / COPY", quantity: 1 },
    { id: 8, docType: "Certificate of Grades for Written Comprehensive Examination", description: "60.00 / COPY", quantity: 1 },
    { id: 9, docType: "Certificate of Grading System", description: "60.00 / COPY", quantity: 1 },
    { id: 10, docType: "Certificate of Graduation/Degree Completion", description: "60.00 / COPY", quantity: 1 },
    { id: 11, docType: "Certificate of Latin Honor", description: "60.00 / COPY", quantity: 1 },
    { id: 12, docType: "Certificate of Units Earned", description: "60.00 / COPY", quantity: 1 },
    { id: 13, docType: "Certificate True Copy of Special Order (S.O.)", description: "50.00 / COPY", quantity: 1 },
    { id: 14, docType: "Certificate of Academic Requirements (CAR)", description: "60.00 / COPY", quantity: 1 },
    { id: 15, docType: "Course Description", description: "60.00 / COPY", quantity: 1 },
    { id: 16, docType: "Diploma - (ISSUED ONLY ONCE AND SUBJECT TO VERIFICATION)n", description: "400.00 / COPY", quantity: 1 },
    { id: 17, docType: "Diploma (Second Copy) - In case the Diploma is lost or whatever reason, you are required to submit a notarized Affidavit of loss or Affidavit of Explanation justifying the request. In case of damaged diploma, the same must be surrendered to UIC for appropriate disposition", description: "400.00 / COPY", quantity: 1 },
    { id: 18, docType: "Honorable Dismissal (issued only once and subject verification)", description: "300.00 / SET", quantity: 1 },
    { id: 19, docType: "Letter of no Objection", description: "60.00 / COPY", quantity: 1 },
    { id: 20, docType: "Official Transcript of Records", description: "250.00 / SET", quantity: 1 },
    { id: 21, docType: "Related Learning Experience (RLE)", description: "150.00/ COPY", quantity: 1 },

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
hero.is-light {
  background-color: #f5f5f5;
}

.uploader {
  margin-top: 20px;
}

.button {
  background-color: #343a40;
  color: #fff;
}

#thumbnail {
  max-width: 100%;
  height: auto;
  display: block;
  margin: 0 auto;
  margin-top: 20px;
}






.div {
  background-color: #d9d9d9;
  display: flex;
  flex-direction: column;
  padding: 0 20px 0 16px;
}
.div-2 {
  color: #000;
  align-self: end;
  margin-top: 18px;
  max-width: 1085px;
  font: 400 30px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-2 {
    max-width: 100%;
    margin-right: 7px;
  }
}
.div-3 {
  background-color: rgba(255, 255, 255, 0.79);
  align-self: end;
  display: flex;
  width: 170px;
  max-width: 100%;
  align-items: flex-start;
  gap: 13px;
  margin: 25px 12px 0 0;
  padding: 15px 17px 15px 8px;
}
@media (max-width: 991px) {
  .div-3 {
    margin-right: 10px;
  }
}
.img {
  aspect-ratio: 1;
  object-fit: contain;
  object-position: center;
  width: 40px;
  overflow: hidden;
  align-self: stretch;
  max-width: 100%;
}
.div-4 {
  color: #000;
  margin: auto 0;
  font: 400 30px Saira Condensed, sans-serif;
}
.div-5 {
  color: #000;
  text-align: justify;
  align-self: end;
  max-width: 1078px;
  margin: 52px 0 54px;
  font: 700 30px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-5 {
    max-width: 100%;
    margin: 40px 5px 40px 0;
  }
}

.navigation {
    align-self: center;
    display: flex;
    margin-top: 62px;
    width: 100%;
    max-width: 1120px;
    align-items: flex-start;
    justify-content: space-between;
    gap: 20px;
  }

  @media (max-width: 991px) {
    .navigation {
      max-width: 100%;
      flex-wrap: wrap;
      margin-top: 40px;
    }
  }
.btnBack {
  font-family: Saira Condensed, sans-serif;
  font-size: 35px;
  font-weight: 700;
  justify-content: center;
  align-items: stretch;
  background-color: #d9d9d9;
  color: #000;
  width: 159px;
  padding: 13px 20px;
  text-align: center;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  border: none;
  margin-bottom: 30px;
}
@media (max-width: 991px) {
  .btnBack {
    margin-top: 0px;
    margin-bottom: 50px;
  }
}
.btnBack:hover{
  background-color:#000;
  color:#f6557e;
}
.btnNext {
  font-family: Saira Condensed, sans-serif;
  font-size: 35px;
  font-weight: 700;
  justify-content: center;
  align-items: stretch;
  background-color: #0d6605;
  color: #ffffff;
  width: 159px;
  padding: 13px 20px;
  text-align: center;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  border: none;
  margin-bottom: 30px;
}
@media (max-width: 991px) {
  .btnNext {
    margin-top: 0px;
    margin-bottom: 50px;
  }
}
.btnNext:hover{
  background-color:#ffffff;
  color:#f6557e;
}
.button-plus:hover{
    background-color: #12a225;
}
.button-minus:hover{
    background-color: #f13a34;
}
.idnum{
    font-weight: 700;
}
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
    width: auto;
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
    width: auto;
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