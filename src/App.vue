<template>
<!-- <ToolBar v-bind:userdata="userdata"/> -->
  <div class="toolbar">
        <div class="logo"><img src="./assets/bonlinelogo.svg" alt=""></div>
        <div class="user_select">
            <div class="icon">
              <i class="fa fa-bell-o" aria-hidden="true">
                <!-- <span class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle">
                      <span class="visually-hidden">New alerts</span>
                  </span>  -->
              </i>
            </div>
            <div class="choose">
              <select v-model='users' class="form-select" aria-label="Default select example">
                <option selected>Choose a User</option>
                <option v-for='users in userdata' v-bind:value='users' :key="users">{{users.first_name}}</option>
              </select>
            </div>
        </div>
    </div>

  <div class="contentholder">
    <div class="sidebar">
      <ul class="list-group">
        <li class="list-group-item">Home</li>
        <li class="list-group-item">Billing</li>
      </ul>
    </div>

    <div class="preview">
      <div v-if="users">
        <!-- <p>Selected User Information:</p> 
        {{users.account_id}}
        {{users.first_name}}
        {{users.last_name}}
        {{users.email_address}}
        {{users.business_name}}
        {{users.address_line_one}}
        {{users.address_line_two}}
        {{users.mobile_number}}
        {{users.phone_number}}
        {{users.address_city}}
        {{users.address_county}}
        {{users.products.product_detail}} -->


        <div class="billing">
          <div class="heading">
            <h2>Billing</h2>
            <p class="mb2 text-muted">Overview of your accounts.</p>
          </div>
          <div class="container">
          <div class="row acc_bubble" style="padding-top: 15px; padding-bottom: 15px;">
            <div class="col-4">
              <div class="card col-12" style="padding-top: 12px;padding-left: 30px;padding-right: 30px;padding-bottom: 12px;border-radius: 5px;">
              <div>{{users.business_name}} <span class="badge rounded-pill bg-secondary">{{users.account_status}}</span></div>
            <div>Account ID: {{users.account_id}}</div>
            </div>
            </div>
            
          </div>
          <hr style="margin-top:0;">

          <div class="row">
            <div class="col-8">
              <div class="card col-12">
                <div class="card-body">
                  <div class="card-header">
                    <h5 class="card-title">Payment details</h5>
                    <h6 class="card-subtitle mb-2 text-muted">View details of your next invoice and payment method.</h6>
                  </div>
                  <div class="card-text" style="margin-top: 10px; margin-bottom: 10px;"><b>Next invoice: </b>{{users.next_invoice_date}}</div>
                  <div class="container row">
                    <div class="col-6">
                      <div class="card col-12 pd_card">
                      <div class="card-body">
                          <h6 class="card-title">Current balance</h6>
                          <h4 class="card-subtitle mb2 text-muted"><b>&#163; {{users.balance}}</b></h4>
                          <p><span><i class="fa fa-lock" aria-hidden="true"></i></span> This is a secure 256-bit SSL encrypted payment. You're safe.</p>
                          <BtnX class="btn btn-primary" text="Pay Now" />
                        </div>
                    </div>
                    </div>
                    <div class="col-6">
                      <div class="card col-12  pd_card">
                      <div class="card-body">
                          <h6 class="card-title">Payment method <span class="badge rounded-pill bg-secondary">{{users.payment_method}}</span></h6>
                          <p class="word"><span><i class="fa fa-lightbulb-o" style="color: #38f000" aria-hidden="true">Guide:</i></span>To manage your payments more easily, we recommend switching to Direct Debit.</p>
                          <BtnX class="btn btn-primary" text="Switch to Direct Debit" /> 
                        </div>
                    </div>
                    </div>
                    
                  </div>
                </div>
              </div>
            </div>
            <div class="col-4">
              <div class="card col-12">
                <div class="card-body">
                  <div class="card-header">
                    <h5 class="card-title">My products</h5>
                    <h6 class="card-subtitle mb-2 text-muted">All your products at a glance</h6>
                  </div>
                  <ul class="list-group list-group-flush">
                    <li class="list-group-item" v-for="product in users.products" :key="product">{{product.product_kind}} - {{product.product_detail}}</li>
                  </ul>
                </div>
              </div>
            </div>
            
          </div>
          <hr>
            <div class="row">
              <div class="col-12">
                <div class="col-12">
                  <div class="card details_account">
                    <div class="card-body">
                      <div class="card-header">
                        <h2 class="card-title">Account Details</h2>
                        <p class="card-subtitle mb2 text-muted">Your account information.</p>
                      </div>
                      <table class="table">
                        <thead>
                          <tr>
                            <th scope="col">#</th>
                            <th scope="col">Firstname</th>
                            <th scope="col">Lastname</th>
                            <th scope="col">Acount ID</th>
                            <th scope="col">Email</th>
                            <th scope="col">Business Name</th>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <th scope="row">1</th>
                            <td>{{users.first_name}}</td>
                            <td>{{users.last_name}}</td>
                            <td>{{users.account_id}}</td>
                            <td>{{users.email_address}}</td>
                            <td>{{users.business_name}}</td>
                          </tr>
                        </tbody>
                      </table>

                    </div>

                  </div>
                </div>
              </div>
            </div>
          </div>
          
        </div>
        
    
    

    

      </div>
      <div v-else>
        Oops nothing to show. Click on the select menu to view user data.
      </div>
    </div>
  </div>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import ToolBar from './components/ToolBar.vue'
import BtnX from './components/BtnX.vue'

export default {
  name: "App",
  components:{
    // ToolBar,
    BtnX
  },
  data(){
    return {
      userdata: [
        {
          account_id: 291123,
          first_name: "Lynda",
          last_name: "Monnoyer",
          email_address: "lmonnoyer0@fema.gov",
          business_name: "Ares Capital Corporation",
          address_line_one: "89652 Continental Plaza",
          address_line_two: "Holmberg",
          mobile_number: "07855521456",
          phone_number: "07855521456",
          address_city: "LONDON",
          address_county: "GREATER LONDON",
          address_country: "UNITED KINGDOM",
          address_post_code: "SW18 5RH",
          account_status: "Live",
          payment_method: "MP",
          next_invoice_date: "2022-03-22",
          balance: 30,
          products: [
            {
              product_id: 70005302,
              product_kind: "VOIP",
              product_detail: "01200400975",
            },
          ],
          authorised_contact: {
            full_name: null,
            email_address: null,
            mobile_number: null,
            phone_number: null,
          },
        },
        {
          account_id: 291321,
          first_name: "Etienne",
          last_name: "Curson",
          email_address: "ecurson1@drupal.com",
          business_name: "Salem Media Group, Inc.",
          address_line_one: "13329 Maple Wood Crossing",
          address_line_two: "Paget",
          mobile_number: "07855521456",
          phone_number: "07855521456",
          address_city: "LONDON",
          address_county: "GREATER LONDON",
          address_country: "UNITED KINGDOM",
          address_post_code: "SW8 1SQ",
          account_status: "Suspended",
          payment_method: "DD",
          next_invoice_date: "2022-04-22",
          balance: 65.25,
          products: [
            {
              product_id: 5004629,
              product_kind: "TELCO",
              product_detail: "SW29BE",
            },
            {
              product_id: 70003198,
              product_kind: "VOIP",
              product_detail: "01200569745",
            },
            {
              product_id: 10003198,
              product_kind: "WEBSITE",
              product_detail: "drupal.com",
            },
          ],
          authorised_contact: {
            full_name: "Linea Bricket",
            email_address: "lbricket2@digg.com",
            mobile_number: "07855521456",
            phone_number: "07855521456",
          },
        },
        {
          account_id: 298461,
          first_name: "Robbi",
          last_name: "Nuscha",
          email_address: "rnuscha4@simplemachines.org",
          business_name: "Carbo Ceramics, Inc.",
          address_line_one: "825 Magdeline Pass",
          address_line_two: "Pine View",
          mobile_number: "07855521456",
          phone_number: "07855521456",
          address_city: "LONDON",
          address_county: "GREATER LONDON",
          address_country: "UNITED KINGDOM",
          address_post_code: "SW8 1SQ",
          account_status: "Cancelled",
          payment_method: "MP",
          next_invoice_date: "2022-06-22",
          balance: 0,
          products: [
            {
              product_id: 70003315,
              product_kind: "VOIP",
              product_detail: "01300647985",
            },
            {
              product_id: 100002198,
              product_kind: "WEBSITE",
              product_detail: "01200569745",
            },
          ],
          authorised_contact: {
            full_name: "Linea Bricket",
            email_address: "simplemachines.org",
            mobile_number: "07855521456",
            phone_number: "07855521456",
          },
        },
      ],
      users: null
    };
  },
  props:['value'],
  watch: {
    users: function() {
        this.$emit('input', this.users);
    }
  },
  
};
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; */
}

.logo{

}

.toolbar{
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 50px;
    width: 100%;
    background-color: rgb(255, 255, 255);
}

.contentholder{
  display: flex;
}

.sidebar{
  width: 150px;
}

.preview{
    border: solid thin;
    width: 100%;
    height: 100%;
    padding-bottom: 20px;
    background-color: #f9f9f9;
}

.logo {
    height: 50px;
    width: 150px;
    display: flex;
}

img{
  max-width: 100%;
}

.heading{
  background-color: #fff;
  padding: 15px;
  border-bottom: solid thin;
}

.pd_card{
    background-color: #f1f1f1;
    border: none;
    border-radius: 7px;
    padding-top: 12px;
    padding-bottom: 12px;
}

.card-header{
  width: 100%;
  padding-left: 0;
  background-color: #fff;
}

.user_select{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 250px;
  height: 50px;
}

.details{
  display: flex;
  justify-content: space-around;
}

/* .payment-details{
  display: flex;
  justify-content: space-around;
} */
.spacer{
  height: 20px;
}
</style>
