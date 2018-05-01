# Airplane-Challenge-I
<!DOCTYPE html>
<html>
<head>
	<title>Airplane!</title>
</head>
<body>
	<style type="text/css">

		#farm {
			background-image: url("academy-airplane-master/academy-airplane-master/farm.jpg");
			width: 900px;
			height: 700px;
		}
		.player {
			position: absolute;
			background-image: url("academy-airplane-master/academy-airplane-master/player.png");
			width: 70px;
			height: 75px;
		}
		.enemy {
			position: absolute;
			background-image: url("academy-airplane-master/academy-airplane-master/enemy.png");
			width: 70px;
			height: 75px;
	</style>
	<div id="farm">
		<div id="players"></div>
		<div id="enemies"></div>
	</div>

	<script type="text/javascript">

		var player = {
			left: 450,
			top: 620
		}

		var enemies = [
			{left: 300, top: 200},
			{left: 450, top: 250},
			{left: 150, top: 150},
			{left: 690, top: 150},
			{left: 360, top: 50},
			{left: 480, top: 50}
		]

		
		function drawPlayer(){
			content = "<div class='player' style='left:"+player.left+"px; top:"+player.top+"px'></div>";
			document.getElementById("players").innerHTML = content;
		}
		drawPlayer();

		function drawEnemies(){
			content = "";
			console.log(enemies);
			for(var idx = 0; idx < enemies.length; idx++){
				content += "<div class='enemy' style='left:"+enemies[idx].left+"px; top:"+enemies[idx].top+"px'></div>";
			}
			document.getElementById("enemies").innerHTML = content;
		}
		drawEnemies();
		
		document.onkeydown = function(e){
			console.log(e);
			if(e.keyCode == 37 && player.left > 0){ //LEFT
				player.left = player.left - 10;
			}
			if(e.keyCode == 39 && player.left < 840){ //RIGHT
				player.left = player.left + 10;
			}
			if(e.keyCode == 38 && player.top > 450){ //UP
				player.top = player.top - 10;
			}
			if(e.keyCode == 40 && player.top < 620){ //Down
				player.top = player.top + 10;
			}
			

			drawPlayer();
		
		}
	</script>

</body>
</html>
