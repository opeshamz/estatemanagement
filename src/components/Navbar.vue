<template>
  <div class="header" id="Navbar">
    <a href="/" class="logo">Logo</a>
    <input class="menu-btn" type="checkbox" id="menu-btn" />
    <label class="menu-icon" for="menu-btn"
      ><span class="nav-icon"></span
    ></label>

    <ul class="menu">
      <li><a href="#dont">HOME</a></li>
      <li><a href="#forget">PROPERTIES</a></li>
      <li><a href="#dont">FOR SALE</a></li>
      <li><a href="#forget">FOR RENT</a></li>
      <li><a href="#dont">ABOUT US</a></li>
      <li><a href="#forget">CONTACT US</a></li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Navbar",
};
</script>

<style scope>

a {
  color: #000;
}
.header {
  background-color:transparent;
  width: 100%;
  z-index: 5;
  margin-right: -30px;
  position: fixed;
  padding: 0px;
  height: 90px;
  
}

.header ul {
  list-style: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  
  
 
  
  
  
}
.header ul a {
  display: block;
  padding: 20px;
  background-color:#6EC1E4;
  text-decoration: none;
  box-shadow: -2px -2px 7px #ffffff, 2px 2px 2px #ceced1;
}
.header ul a:hover {
  content: '';
box-shadow: inset -3px -3px 7px #ffffff, inset 3px 3px 5px #ceced1;
}
.header .logo {
  float: left;
  display: block;
  padding: 10px 20px;
  font-size: 2rem;
}
.header .menu {
  clear: both;
  max-height: 0px;
  transition: max-height 0.2s cubic-bezier(0.165, 0.6, 0.44, 1);
  z-index: 3;
}
.header .menu-icon {
 
  padding: 28px 20px;
  position: relative;
  float: right;
  cursor: pointer;
}
.header .menu-icon .nav-icon {
  background-color: turquoise;
  display: block;
  height: 2px;
  width: 25px;
  position: relative;
  transition: background 0.2s ease-out;
}
.header .menu-icon .nav-icon::before {
  background: black;
  content: "";
  display: block;
  height: 100%;
  width: 100%;
  position: absolute;
  top: 5px;
}
.header .menu-icon .nav-icon::after {
  background: rgb(92, 25, 25);
  content: "";
  display: block;
  height: 100%;
  width: 100%;
  position: absolute;
  top: -5px;
}
.header .menu-btn {
  display: none;
}
.header .menu-btn:checked ~ .menu {
  max-height: 240px;
 
}
.header .menu-btn:checked ~ .menu-icon .nav-icon {
  background: transparent;
}
.header .menu-btn:checked ~ .menu-icon .nav-icon::before {
  transform: rotate(-45deg);
  top: 0;
}
.header .menu-btn:checked ~ .menu-icon .nav-icon::after {
  transform: rotate(45deg);
  top: 0;
}


@media (min-width: 48em) {
  
  .header li {
    float: left;
    background-color: transparent;
    
   
  }
  .header ul {
    margin-top: 10px;
  }
  
.header ul a {
    margin: 6px;
    border-radius: 5px;
 
}
  .header .menu {
    clear: none;
    float: right;
    max-height: none;
  }

  .header .menu-icon {
    display: none !important;
  }
  

  
}
</style>
