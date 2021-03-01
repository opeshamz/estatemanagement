<template>
    <div id="app">
		<link href="https://fonts.googleapis.com/css?family=Roboto|Poppins" rel="stylesheet">
		<meta name="viewport" content="width=device-width">
		<header>
			<div class="wrap">
				<div id="hamburger" v-on:click="display_menu()">
					<span></span>
					<span></span>
					<span></span>
				</div>
				<img src="https://humancoders-formations.s3.amazonaws.com/uploads/course/logo/104/thumb_bigger_formation-vue-js.png" alt="logo">
				<nav id="menu">
					<li><a>Menu 1</a></li>
					<li class="drop"><a v-on:click="display_drop_menu()">Menu 2 dropdown <i class="icon-arrow"></i></a>
						<ul class="drop_menu">
							<a>Sub menu 1</a>
							<a>Sub menu 2</a>
							<a>Sub menu 3</a>
						</ul>
					</li>
					<li class="drop"><a v-on:click="display_drop_menu()">Menu 3 dropdown  <i class="icon-arrow"></i></a>
						<ul class="drop_menu">
							<a>Sub menu 1</a>
							<a>Sub menu 2</a>
							<a>Sub menu 3</a>
						</ul>
					</li>
					<li><a>Menu 4</a></li>
				</nav>
			</div>
		</header>
		<div id="loader" v-if="load">
			<span></span>
			<span></span>
			<span></span>
			<span></span>
			<span></span>
			<span></span>
			<span></span>
			<span></span>
			<span></span>
		</div>
		<div id="overlay" v-if="load"></div>
		<div id="background">
			<h3>This menu is responsive, resized on.</h3>
			<h3>The header is hide when scroll down and show when scroll up, try it !</h3>
			<button v-on:click="loaded()">Click here for show the loader !</button></button>
		</div>
	</div>
</template>
<script>
var app = new Vue({
  el: '#app',
  data: {
			load : false,
	},
	methods: {
		display_menu : function(){
			var body = document.getElementsByTagName("body")[0];
			(!body.classList.contains("display_menu")) ? body.classList.add("display_menu") : body.classList.remove("display_menu");
		},
		display_drop_menu : function(){
			var drop_menu = event.target.parentElement.getElementsByClassName("drop_menu")[0];
			var drop_menus = document.getElementsByClassName("drop_menu");

			Array.from(drop_menus).forEach(function(e){
				if(e != drop_menu){
					e.classList.remove("display");
				}
			});
			var lis = document.getElementById("menu").getElementsByTagName("li");
			Array.from(lis).forEach(function(e){
				e.style.marginTop = 0;
			});
			(!drop_menu.classList.contains("display")) ? drop_menu.classList.add("display") : drop_menu.classList.remove("display");
			if(window.innerWidth < 660 && drop_menu.classList.contains("display")) {
				event.target.parentElement.nextSibling.nextSibling.style.marginTop = drop_menu.clientHeight + "px";
			}
		},
		loaded : function(){
        	document.getElementsByTagName("body")[0].style.overflowY = "hidden";
      console.log('t');
        	(this.load) ? this.load = false : this.load = true;
		}
	}
});
function close_all_menu() {
	var lis = document.getElementById("menu").getElementsByTagName("li");
	Array.from(lis).forEach(function(e){
		e.style.marginTop = 0;
	});
	var drop_menus = document.getElementsByClassName("drop_menu");
	Array.from(drop_menus).forEach(function(e){
		e.classList.remove("display");
	});
}


</script>