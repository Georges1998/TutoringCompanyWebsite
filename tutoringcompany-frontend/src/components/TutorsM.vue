<!DOCTYPE html>
<template>
<html lang="en">
  <head>
    <title>Manage Tutors</title>
  </head>
  <body>
  <nav class="navbar navbar-expand-lg navbar-light bg-light static-top">
    <!-- <div class="container"> -->
    <router-link to="/HomePage" class="navbar-brand mr-0" style="max-width:calc((1em + 1vw) * 7 + .5rem + 1vw + 30px);font-size:calc(1em + 1vw);">
      <img
        alt="Brand"
        src="../assets/quality.png"
        class="image-responsive mr-2"
        style="max-width:calc(30px + 1vw);overflow: visible;"
      />Quality Academy
    </router-link>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarResponsive"
      aria-controls="navbarResponsive"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    
    <div class="collapse navbar-collapse" id="navbarResponsive">
      <!-- <div class="float-right"> -->
      <ul class="navbar-nav ml-auto">
        <li class="nav-item">
          <router-link to="/ManagerHomePage" class="nav-link">Manager Home</router-link>
        </li>
        <li class="nav-item active">
          <router-link to="/TutorsM" class="nav-link">
            Tutors
            <span class="sr-only">(current)</span>
          </router-link>
        </li>
        <li class="nav-item">
          <router-link to="/StudentsM" class="nav-link">Students</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/CoursesM" class="nav-link">Courses</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/RoomsM" class="nav-link">Rooms</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/SessionsM" class="nav-link">Sessions</router-link>
        </li>
      </ul>
      <!-- </div> uncomment for main links left justified--> 
      <ul class="navbar-nav ml-auto">
        <li class="nav-item dropdown">
            <a class="nav-link" href="#" id="navbarDropdown" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <i class="fa fa-user"></i>
              <i class="fa fa-caret-down"></i>
            </a>
            <div class="dropdown-menu dropdown-menu-right" aria-labelledby="navbarDropdown">
                <a class="dropdown-item" href="#">Profile</a>
                <a @click="ManagerLogout()" class="dropdown-item" >Logout</a>
            </div>
        </li>
      </ul>
    </div>
    <!-- </div> uncomment to make the nav bar more narrow -->
  </nav>
  <div class="jumbotron jumbotron-fluid">
    <div class="container">
      <h1 class="display-4">Tutors</h1>
      <p
        class="lead"
      >Gallery of all tutors, click on the name of any tutor to access and manage their profile.</p>
    </div>
  </div>
  <div class="container-fluid">
    <div class="row">
      <div v-for="tutor in tutors" class="col-12 col-md-6 col-lg-4 col-xl-3 mb-4">
        <div class="card mx-auto text-center">
          <div class="card-body">
            <h4 class="card-title">
              <router-link v-bind:to="'/TutorPage/' + tutor.email">{{ tutor.first_name }} {{tutor.last_name}}</router-link>
            </h4>
            <h6 class="card-subtitle mb-2 text-muted">Tutor 
              <span v-if="tutor.verified" class="badge badge-pill badge-success">Verified ✔</span>
            </h6>
            <p
              class="card-text"
            ></p>
          </div>
          <ul class="list-group list-group-flush">
            <li class="list-group-item">Email: {{tutor.email}}</li>
            <li class="list-group-item">Phone #: {{tutor.phone_number}}</li>
            <li class="list-group-item">Verified: {{tutor.verified}}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
  </body>
</html>
</template>

<script src="./tut.js">
</script>

<style>
.card {
  max-height: 100rem;
}
</style>