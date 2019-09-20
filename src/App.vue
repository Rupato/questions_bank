<template>
  <div id="app">
    <div id="nav">
  <div class="top-bar">

            <div class="col-md-1">
              <img src ="./assets/ninestack_logo.png" style="width:100%">
              <!-- <p>Contact us on +91 7568 54 3012 or dkstudioin@gmail.com.</p> -->
              
            </div>
              <div class="col-md-11">
              </div>
            <!-- <div class="col-md-6">
              <div class="d-flex justify-content-md-end justify-content-between">
                <ul class="list-inline contact-info d-block d-md-none">
                  <li class="list-inline-item"><a href="#"><i class="fa fa-phone"></i></a></li>
                  <li class="list-inline-item"><a href="#"><i class="fa fa-envelope"></i></a></li>
                </ul>
                <div class="login"><a href="#" data-toggle="modal" data-target="#login-modal" class="login-btn"><i class="fa fa-sign-in"></i><span class="d-none d-md-inline-block">Sign In</span></a><a href="customer-register.html" class="signup-btn"><i class="fa fa-user"></i><span class="d-none d-md-inline-block">Sign Up</span></a></div>
                <ul class="social-custom list-inline">
                  <li class="list-inline-item"><a href="#"><i class="fa fa-facebook"></i></a></li>
                  <li class="list-inline-item"><a href="#"><i class="fa fa-google-plus"></i></a></li>
                  <li class="list-inline-item"><a href="#"><i class="fa fa-twitter"></i></a></li>
                  <li class="list-inline-item"><a href="#"><i class="fa fa-envelope"></i></a></li>
                </ul>
              </div>
            </div> -->
       
      </div>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/editor">Editor</router-link>
    </div>
    <router-view/>
  </div>
</template>




<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#background_image{
// background-image: url("assets/ninestack banner.jpg");
// background-color:red;

}


#nav {
  padding:  0px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
