<template>
  <div>
    <nav class="navbar navbar-expand-lg bg-body-tertiary  border-bottom border-2" style="border-color:#c9c9c9!important">
  <div class="container-fluid">
        <div>
            <span style="font-size:20px;cursor:pointer" class="me-3"  v-show="sidebarbool" @click="$emit('changestate')" >&#9776;</span>
            <a class="navbar-brand">Dashboard</a>
        </div>
    <button class="navbar-toggler mb-3" type="button" data-bs-toggle="collapse" data-bs-target="#navbarTogglerDemo02" aria-controls="navbarTogglerDemo02" aria-expanded="false" aria-label="Toggle navigation">
      <span class="">&#9776;</span>
    </button>
    <div class="collapse navbar-collapse" id="navbarTogglerDemo02">
        <form class="d-flex  mx-auto mb-2 mb-lg-0" role="search">
            <input type="search"  placeholder="Search here" class="search-field px-3 py-1" />
            <button type="submit" class="search-button">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search " viewBox="0 0 16 16">  <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"/></svg>
            </button>
        </form>

      <ul class="navbar-nav d-flex">
        <li class="nav-item">
<div>
        <div class="d-flex">
            <span  class="border-2 notify rounded-circle" style="padding-inline: 0.6rem !important; height: fit-content; padding-block: 0.30rem !important; background-color:rgb(238, 238, 238)">
                <i class="bi bi-bell position-relative fs-5">
                    <span class="position-absolute top-0 start-100 translate-middle p-1 bg-danger border border-light rounded-circle">
                    <span class="visually-hidden"></span>
                </span>
                </i>
            </span>
        
            <div class="ms-4 me-2">
                <p class="text-dark fw-bolder my-0">Alex Mora</p>
                <p class="text-muted fw-normal" style="font-size:12px">Alex Mora</p>
            </div>
            <img src="../assets/profileImg.jpg" alt="Avatar" class="portfolio-img" style="width:50px; height:50px">
        </div>        
        </div>
        </li>
      </ul>

    </div>
  </div>
</nav>
    <!-- <nav class="navbar bg-body-tertiary border-bottom border-2" style="border-color:#c9c9c9!important">
      <div class="container-fluid">
        <div>
            <span style="font-size:20px;cursor:pointer" class="me-3"  v-show="sidebarbool" @click="$emit('changestate')" >&#9776;</span>
                <a class="navbar-brand">Dashboard</a>
        </div>
        
        <form class="d-flex" role="search">
            <input type="search"  placeholder="Search here" class="search-field form-control form-control-sm" />
            <button type="submit" class="search-button">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16">  <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"/></svg>
            </button>
        </form>
        <div>
        <div class="d-flex">
            <span  class="border-2 notify rounded-circle" style="padding-inline: 0.6rem !important; height: fit-content; padding-block: 0.30rem !important; background-color:rgb(238, 238, 238)">
                <i class="bi bi-bell position-relative fs-5">
                    <span class="position-absolute top-0 start-100 translate-middle p-1 bg-danger border border-light rounded-circle">
                    <span class="visually-hidden"></span>
                </span>
                </i>
            </span>
        
            <div class="ms-4 me-2">
                <p class="text-dark fw-bolder my-0">Alex Mora</p>
                <p class="text-muted fw-normal" style="font-size:12px">Alex Mora</p>
            </div>
            <img src="../assets/profileImg.jpg" alt="Avatar" class="portfolio-img" style="width:50px; height:50px">
        </div>        
        </div>
      </div>
    </nav> -->
  </div>
</template>
<script>
export default {
    emits: ['changestate'],
    props: {
        sidebarbool: Boolean
    }
};
</script>
<style >
.portfolio-img {
  border-radius: 50%;
  object-fit: cover;
}
.notify{
    border: 2px solid rgb(176, 176, 176) ;
}
form {
  display: flex;
  flex-direction: row;
}
.search-field {
    background-color: rgb(238, 238, 238);
    border: none;
    width: 3in !important;
    border-radius: 100px;
    outline: none;
}

.search-button {
  background: transparent;
  border: none;
  outline: none;
  margin-left: -33px;
}

.search-button svg {
  width: 20px;
  height: 20px;
  object-fit: cover;
    color: rgb(69, 69, 69);
}
.start-100 {
    left: 80% !important;
}
.top-0 {
    top: 4px !important;
}
</style>