<template>
      <nav>
        <div class="nav-start">
            <div @click="toggleHam" class="bars">
                <div :class="{ change: isChange }" class="bar1"></div>
                <div :class="{ change: isChange }" class="bar2"></div>
                <div :class="{ change: isChange }" class="bar3"></div>
            </div>
            <h1 class="nav-image">Sneakers</h1>
            <ul class="nav-items"  :class="{ change: isChange }">
                <li><a href="#">Collections</a></li>
                <li><a href="#">Men</a></li>
                <li><a href="#">Women</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </div>
        <div class="nav-end">
        <i class="fa-solid fa-cart-shopping"></i>
            <img src="../assets/images/avatar.jpg" alt="" class="nav_avatar">
        </div>
      </nav>
</template>

<script>
export default {
    data() {
        return {
            isChange: false,
        }
    },
    methods: {
        toggleHam(){
            this.isChange = !this.isChange
        }
    },
}
</script>

<style scoped>
nav{
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #efeef1;
    padding: 10px 0;
   
}
.nav-start, .nav-end{
    display: flex;
    align-items: center;
}
ul.nav-items{
    display: flex;
    list-style: none;
    margin-left: 15px;

}
ul.nav-items li{
    margin-left: 18px;
}
.nav-items a{
    text-decoration: none;
    color: #b0b1b3;
    font-weight: 600;
}
.nav-image{
    font-family: 'Kdam Thmor Pro', sans-serif;

}
.fa-solid{
    font-size: 1.5rem;
    margin-right: 2rem;
}
.nav_avatar{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    
}
.bars{
  cursor: pointer;
  margin-right: 7px;
  display: none;
}
.bar1, .bar2, .bar3 {
  width: 20px;
  height: 4px;
  background-color: #333;
  margin: 6px;
  transition: 0.4s;
}

.change.bar1 {
  -webkit-transform: rotate(-45deg) translate(-9px, 6px);
  transform: rotate(-45deg) translate(-9px, 6px);
}

.change.bar2 {opacity: 0;}

.change.bar3 {
  -webkit-transform: rotate(45deg) translate(-8px, -8px);
  transform: rotate(45deg) translate(-8px, -8px);
}
@media(max-width:920px){
  ul.nav-items{
      display: none;
  }
  ul.change{
      display: block;
      position: absolute;
      top:80px;
      width: 80%;
      background: black;
      padding: 15px;
      color: #fff;
      border-radius: 5px;
      z-index: 10000;
  }
  ul.change li a{
      margin-top: 10px;
      color: #fff;
  }
  .bars{
      display: inline-block;
  }
}
</style>