<template>
 <div class="section">
   <div class="row">
     <div class="product_images">
       <img :src="image" alt="" class="main_image">
       <div class="product_variants">
        <div v-for="(variant, index) in variantImage" :key="variant.id">
         <img :src="variant.url" class="image_variant" @click="clickedImage(index)" >
         
        </div>
       </div>
     </div>
     <Carousel class="openCarousel" />
     <div class="product_overview">
       <span class="product_company">Sneaker Company</span>
       <h3 class="heading">Fall Limited Edition Sneakers</h3>
       <p class="product_body">The low-profile sneakers are your perfect casual wear companion. Featuring a durable rubber outer sole. they'll withstand everything the weather can offer.</p>
       <div class="row_product">
         <p class="product_price">$125.00 <span class="percent">50%</span></p>
         <span class="slashed_price">$250.00</span>
       </div>
       
       
       <div class="row-cart cart">
         <div class="cart_operators">
           <button @click="subtractCount" class="operator-left">-</button>
            <input type="text" :value="count" readonly class="counter">
            <button @click="addCount" class="operator-right">+</button>
         </div>
         
         <a href=""><button class="btn"><i class="fa-solid fa-cart-shopping"></i>Add to cart</button></a>
         
       </div>
       
     </div>
   </div>
   
 </div>
</template>

<script>
// @ is an alias to /src

import Carousel from '@/components/Carousel'
export default {
  name: 'HomeView',
  components: {
    Carousel
  },
  data() {
    return {
      count: 1,
      selectedImageIndex: 0,
      variantImage: [
        {
          id:1,
          alt: 'white',
          url: require('../assets/images/1.jpg')
        },
        {
          id:2,
          alt: 'red',
          url: require('../assets/images/2.jpg')
        },
        {
          id:3,
          alt: 'blue',
          url: require('../assets/images/3.jpg')
        },
        {
          id:4,
          alt: 'pink',
          url: require('../assets/images/4.jpg')
        },
      ]
    }
  },
  methods: {
    clickedImage(index){
      return this.selectedImageIndex = index;
    },
    addCount(){
      this.count++;
    },
    subtractCount(){
      if(this.count <= 1){
        return this.count;
      }
      this.count--;
    }
  },
  computed: {
    image(){
      return this.variantImage[this.selectedImageIndex].url;
    },
    
    
  },

}
</script>
<style scoped>
a{
  text-decoration: none;
}
.row{
  display: flex;
  padding: 50px 30px;
  justify-content: space-around;
  align-items: center;
  flex-wrap: wrap;
}
.product_images{
flex-basis: 40%;

}
.main_image{
 width: 100%;
 height: 400px;
 object-fit: cover;
 border-radius: 10px;
  
}
.openCarousel{
  display: none;
}
.product_overview{
 flex-basis: 35%;
 padding: 20px 0;

}
.product_variants{
  display: grid;
  grid-template-columns:repeat(4, 1fr);
  align-items: stretch;
  gap: 0 5px;
  padding: 15px 0;

}
.image_variant{
  width: 100px;
  height: 70px;
  border-radius: 5px;
  object-fit: cover;
  cursor: pointer;
  
}
.image_variant:hover{
  opacity: .3;
  border: 2px solid #ff7d1b;
}

span.product_company{
display: block;
text-transform: uppercase;
color: #ff7d1b;
font-weight: 500;
font-size: .8rem;
letter-spacing: 3px;
}
.heading{
font-size: 2rem;
text-transform: capitalize;
padding-top: 10px;
line-height: 1.1;
}
.product_body{
  font-size: 1rem;
  line-height: 1.2;
  color: #9da0a6;
  padding: 20px 0;
}
.product_price{
  font-size: 1.5rem;
  font-weight: bold;
}
div.row_product{
  display: flex;
  flex-direction: column;
}
.row_product .percent{
padding: 5px;
  margin-left: 10px;
  background: #faefe3;
  color: #ff7d1b;
  font-size: .8rem;
}

.slashed_price{
  text-decoration: line-through;
  color: #9da0a6;
}
.row-cart{
  display: flex;

}
.cart{
    margin: 15px 0;
}
.cart_operators{

 background-color: #fff;
 display: flex;
 margin-right: 10px;
}
.counter{
width: 2.5rem;
text-align: center;
border: none;
background: #f7f8fd;
padding: 11px 0 7px;

}
.operator-left, .operator-right{
 color: #ff7d1b;
 background: #f7f8fd;
 border: none;
cursor: pointer;
font-size: 1.375rem;
text-align: center;
width: 1.875rem;
padding:5px;
}
.operator-left{
border-top-left-radius: 5px;
border-bottom-left-radius: 5px;
}
.operator-right{
border-top-right-radius: 5px;
border-bottom-right-radius: 5px;
}


.btn{
  padding: 10px 40px;
  cursor: pointer;
  color: #fff;
  font-size: 1rem;
  background: #ff7d1b;
  border: none;
  border-radius: 10px;
  display: inline-block;
}
.cart .fa-solid{
  margin-right: 10px;
}

@media(max-width:950px){
  
}
@media(max-width:770px){
  .product_overview{
    flex-basis: 100%;
  }
 .section .row{
    padding: 0;
  }
  .product_variants{
    display: none;
  }
  .product_images{
    display: none;
  }
  div .row_product{
    flex-direction: row;
    justify-content: space-between;
    align-items: baseline;
  }
  .row-cart{
    flex-direction: column;
  }
  .counter{
    width: 60%;
  }
  .operator-left, .operator-right{
    width: 20%;
  }
  
  .cart_operators{
    display: block;
    width:100%;
  }
 .btn{
   margin: 15px 0;
   width: 100%;
 }
 .openCarousel{
   display: block;
 }
}
@media(max-width:430px){

}

</style>
