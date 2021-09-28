<template>
    <div class="login">
        <!--Main Navigation-->
  <header>

    <!--Intro Section-->
    <section class="view intro-2">
      <div class="mask rgba-stylish-strong h-100 d-flex justify-content-center align-items-center">
        <div class="container">
          <div class="row">
            <div class="col-xl-5 col-lg-6 col-md-10 col-sm-12 mx-auto mt-lg-5">

              <!--Form with header-->
              <div class="card wow fadeIn" data-wow-delay="0.3s">
                <div class="card-body">

                  <!--Header-->
                  <div class="form-header purple-gradient">
                    <h3>Autentificare</h3>
                  </div>
                  <form id="login" @submit.prevent="login()">
                  <div class="md-form">
                    <i class="fas fa-envelope prefix white-text"></i>
                    <input type="text" name="email" id="orangeForm-email" class="form-control" required="required" v-model="email">
                    <label for="orangeForm-email"><font-awesome-icon icon="envelope" /> E-mail</label>
                  </div>

                  <div class="md-form">
                    <i class="fas fa-lock prefix white-text"></i>
                    <input type="password" name="parola" id="orangeForm-pass" class="form-control" required="required" v-model="password">
                    <label for="orangeForm-pass"><font-awesome-icon icon="key" /> Parola</label>
                  </div>

                  <div class="text-center">
                    <button type="submit" class="btn purple-gradient btn-lg">Autentificare <font-awesome-icon icon="sign-in-alt" /></button>
                  </div>
                  </form>
                </div>
              </div>
              <!--/Form with header-->

            </div>
          </div>
        </div>
      </div>
    </section>

  </header>
  <!--Main Navigation-->
    </div>
</template>

<script>

import axios from 'axios';

export default {
    name: 'Login',
    data(){
      return {
        email: '',
        password: ''
      }
    },
    methods: {
      login(){
        axios.post('https://medics.bistrita-webdesign.ro/login.php' , {email: this.email , password: this.password})
        .then((res) => {
          console.log(res);
        });
      }
    }
}
</script>


<style scoped>
html,
        body,
        header,
        .view {
          height: 100vh;
        }

        @media (max-width: 740px) {
          html,
          body,
          header,
          .view {
            height: 815px;
          }
        }

        @media (min-width: 800px) and (max-width: 850px) {
          html,
          body,
          header,
          .view  {
            height: 650px;
          }
        }

        .intro-2 {
            background: url("https://business-review.eu/wp-content/uploads/2020/09/foto-articol-delivery-ovidiu.jpg")no-repeat center center;
            background-size: cover;
        }
        .top-nav-collapse {
            background-color: #3f51b5 !important;
        }
        .navbar:not(.top-nav-collapse) {
            background: transparent !important;
        }
        @media (max-width: 768px) {
            .navbar:not(.top-nav-collapse) {
                background: #3f51b5 !important;
            }
        }
        @media (min-width: 800px) and (max-width: 850px) {
            .navbar:not(.top-nav-collapse) {
                background: #3f51b5!important;
            }
        }

        .card {
            background-color: rgba(229, 228, 255, 0.2);
        }
        .md-form label {
            color: #ffffff;
        }
        h6 {
            line-height: 1.7;
        }


        .card {
            margin-top: 30px;
            /*margin-bottom: -45px;*/

        }

        .md-form input[type=text]:focus:not([readonly]),
        .md-form input[type=password]:focus:not([readonly]) {
            border-bottom: 1px solid #8EDEF8;
            box-shadow: 0 1px 0 0 #8EDEF8;
        }
        .md-form input[type=text]:focus:not([readonly])+label,
        .md-form input[type=password]:focus:not([readonly])+label {
            color: #8EDEF8;
        }

        .md-form .form-control {
            color: #fff;
        }
</style>