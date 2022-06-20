<template>
    <div>
        <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="../assets/images/1.jpg" class="d-block w-100" alt="">
    </div>
    <div class="carousel-item">
      <img src="../assets/images/2.jpg" class="d-block w-100" alt="">
    </div>
    <div class="carousel-item">
      <img src="../assets/images/3.jpg" class="d-block w-100" alt="">
    </div>
    <div class="carousel-item">
      <img src="../assets/images/4.jpg" class="d-block w-100" alt="">
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
    <i class="fa-solid fa-chevron-left"></i>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
    <i class="fa-solid fa-chevron-right"></i>
  </button>
</div>  
    </div>
</template>

<style>
     .carousel-inner > .carousel-item > img{ 
         height:300px; 
         object-fit: cover;
         
         }
         .fa-chevron-left, .fa-chevron-right{
             border-radius: 50%;
             padding: 5px;
             font-size: 18px;
             color: #000;
             background: #fff;
         }
</style>