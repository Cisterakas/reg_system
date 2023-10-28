<script setup>
import Footer from './Footer.vue';
import NavigationBar from './NavigationBar.vue';
</script>
<template>
  <NavigationBar />
  <div class="div">
    <div class="div-2">
      <div class="div-3">
        <span style="color: rgba(255, 255, 255, 1)"
          >This is the University of the Immaculate Conception’s online request
          for documents exclusively for the use of UIC students and alumni
          only.<br /><br /></span
        ><span style="color: rgba(0, 0, 0, 1)"
          >PRIVACY CONSENT I hereby agree and consent the University of the
          Immaculate Conception may collect, use, disclose and process my
          personal information set out in this form and/or otherwise provided by
          me for the purpose of requesting school documents as stated in the
          R.A. 10173, otherwise known as the Data Privacy Act of 2012 and other
          related data privacy policies. <br />The information will only be
          accessed by authorized university staff. I understand that my data
          will be held securely and will not be disclosed to third parties
          without my permission. When this information is no longer required,
          official university procedure will be followed to dispose my data.
          <br />By choosing an option I represent and warrant that I am the data
          subject and that I have read and understood all the conditions and
          reminders in connection with this request and agree to comply with
          them. By clicking selecting an option, I also certify that the
          information given are true to the best of my knowledge and belief.<br /><br />Please
          select one of the following options, according to your situation, to
          start your request:</span
        >
      </div>
      <div class="div-4">
        <div class="div-5">
          <div class="column">
            <div class="div-6">
              <div class="div-7">
                <div class="div-8">OPTION A</div>
                <div class="div-9">
                  Please select this option if you have your MYUIC account.
                </div>
                <div class="div-10"><div class="div-11">SELECT</div></div>
              </div>
            </div>
          </div>
          <div class="column-2">
            <div class="div-12">
              <div class="div-13">
                <div class="div-14">OPTION B</div>
                <div class="div-15">
                  Please select this option if you do not have a MYUIC account.
                </div>
                <div class="div-16"><div class="div-17">SELECT</div></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="div-18"><div class="div-19">BACK</div></div>
    </div>
  </div>
 
<Footer />
</template>
<style scoped>
.div {
  background-color: #f6557e;
  display: flex;
  flex-direction: column;
  padding: 0 20px;
}
.div-2 {
  align-self: center;
  display: flex;
  width: 100%;
  max-width: 1260px;
  flex-direction: column;
  margin: 49px 0 53px;
}
@media (max-width: 991px) {
  .div-2 {
    max-width: 100%;
    margin: 40px 0;
  }
}
.div-3 {
  color: #000;
  text-align: justify;
  align-self: end;
  max-width: 1155px;
  font: 400 40px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-3 {
    max-width: 100%;
  }
}
.div-4 {
  align-self: center;
  margin-top: 78px;
  width: 100%;
  max-width: 1151px;
}
@media (max-width: 991px) {
  .div-4 {
    max-width: 100%;
    margin-top: 40px;
  }
}
.div-5 {
  gap: 20px;
  display: flex;
}
@media (max-width: 991px) {
  .div-5 {
    flex-direction: column;
    align-items: stretch;
    gap: 0px;
  }
}
.column {
  display: flex;
  flex-direction: column;
  line-height: normal;
  width: 50%;
  margin-left: 0px;
}
@media (max-width: 991px) {
  .column {
    width: 100%;
  }
}
.div-6 {
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  background-color: #fff;
  display: flex;
  flex-grow: 1;
  flex-direction: column;
  width: 100%;
  margin: 0 auto;
  padding: 53px 20px 72px;
}
@media (max-width: 991px) {
  .div-6 {
    max-width: 100%;
    margin-top: 40px;
  }
}
.div-7 {
  align-self: center;
  display: flex;
  width: 423px;
  max-width: 100%;
  flex-direction: column;
}
.div-8 {
  color: #f986a3;
  margin-left: 21px;
  font: 700 45px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-8 {
    margin-left: 10px;
    font-size: 40px;
  }
}
.div-9 {
  color: #f6557e;
  align-self: stretch;
  margin-top: 30px;
  font: 400 40px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-9 {
    max-width: 100%;
  }
}
.div-10 {
  justify-content: center;
  align-items: center;
  background-color: #d9d9d9;
  align-self: center;
  display: flex;
  width: 133px;
  max-width: 100%;
  flex-grow: 1;
  flex-direction: column;
  margin: 33px 0 0 -16px;
  padding: 0 20px;
}
.div-11 {
  color: #f986a3;
  align-self: center;
  text-wrap: nowrap;
  font: 700 35px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-11 {
    text-wrap: initial;
  }
}
.column-2 {
  display: flex;
  flex-direction: column;
  line-height: normal;
  width: 50%;
  margin-left: 20px;
}
@media (max-width: 991px) {
  .column-2 {
    width: 100%;
  }
}
.div-12 {
  background-color: #fff;
  display: flex;
  flex-grow: 1;
  flex-direction: column;
  width: 100%;
  margin: 0 auto;
  padding: 53px 20px 72px;
}
@media (max-width: 991px) {
  .div-12 {
    max-width: 100%;
    margin-top: 40px;
  }
}
.div-13 {
  align-self: center;
  display: flex;
  width: 424px;
  max-width: 100%;
  flex-direction: column;
}
.div-14 {
  color: #f986a3;
  margin-left: 21px;
  font: 700 45px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-14 {
    margin-left: 10px;
    font-size: 40px;
  }
}
.div-15 {
  color: #f6557e;
  align-self: stretch;
  margin-top: 35px;
  font: 400 40px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-15 {
    max-width: 100%;
  }
}
.div-16 {
  justify-content: center;
  align-items: center;
  background-color: #d9d9d9;
  align-self: center;
  display: flex;
  width: 132px;
  max-width: 100%;
  flex-grow: 1;
  flex-direction: column;
  margin: 36px 0 0 14px;
  padding: 0 20px;
}
.div-17 {
  color: #f986a3;
  align-self: center;
  text-wrap: nowrap;
  font: 700 35px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-17 {
    text-wrap: initial;
  }
}
.div-18 {
  justify-content: center;
  align-items: center;
  background-color: #d9d9d9;
  align-self: start;
  display: flex;
  margin-top: 116px;
  width: 159px;
  max-width: 100%;
  flex-grow: 1;
  flex-direction: column;
  padding: 13px 20px;
}
@media (max-width: 991px) {
  .div-18 {
    margin-top: 40px;
  }
}
.div-19 {
  color: #000;
  align-self: center;
  text-wrap: nowrap;
  font: 700 30px Saira Condensed, sans-serif;
}
@media (max-width: 991px) {
  .div-19 {
    text-wrap: initial;
  }
}
</style>