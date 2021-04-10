# 3D-Bouncing-ball-with-css3
.....html.....
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>repl.it</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
    <h2>Click and hold the ball to move it back</h2>
  </head>
  <body>
    <div id="ballWrapper">
	<div id="ball"></div>
	<div id="ballShadow"></div>			
</div>	
  </body>
</html>
.....css.....
#ballWrapper {
	width: 140px;
	height: 300px;
	position: fixed;
	left: 50%;
	top: 50%;
	margin: -150px 0 0 -70px;
}
#ball {
	width: 140px;
	height: 140px;
	border-radius: 70px;
	background: linear-gradient(top,  rgba(209, 7, 7, 0.87) 0%,rgba(212, 6, 6, 0.24) 99%);
	box-shadow: inset 0 -5px 15px rgba(255,255,255,0.4), 
				inset -2px -1px 40px rgba(0,0,0,0.4), 
				0 0 1px #000;	
}
#ball::after {
	content: "";
	width: 80px; 
	height: 40px; 
	position: absolute;
	left: 30px;
	top: 10px;	
	background: linear-gradient(top,  rgba(232,232,232,1) 0%,rgba(232,232,232,1) 1%,rgba(255,255,255,0) 100%);
	border-radius: 40px / 20px;	
}
#ballShadow {
	width: 60px;
	height: 75px;
	position: absolute;
	z-index: 0;
	bottom: 0;
	left: 50%;
	margin-left: -30px;
	background: rgba(20, 20, 20, .1);
	box-shadow: 0px 0 20px 35px rgba(20,20,20,.1);
	border-radius: 30px / 40px;	
}
#ball {
	animation: jump 1s infinite;
}
@keyframes jump {
	0% {
		top: 0;
	}
	50% {
		top: 140px;
		height: 140px;
	}
	55% {
		top: 160px; 
		height: 120px; 
		border-radius: 70px / 60px;
	}
	65% {
		top: 120px; 
		height: 140px; 
		border-radius: 70px;
	}
	95% {
		top: 0;
	}
	100% {
		top: 0;
	}
}
#ballShadow {
	animation: shrink 1s infinite;
}
@-keyframes shrink {
	0% {
		bottom: 0;
		margin-left: -30px;
		width: 60px;
		height: 75px;
		background: rgba(20, 20, 20, .1);
		box-shadow: 0px 0 20px 35px rgba(20,20,20,.1);
		border-radius: 30px / 40px;
	}
	50% {
		bottom: 30px;
		margin-left: -10px;
		width: 20px;
		height: 5px;
		background: rgba(20, 20, 20, .3);
		box-shadow: 0px 0 20px 35px rgba(20,20,20,.3);
		border-radius: 20px / 20px;
	}
	100% {
		bottom: 0;
		margin-left: -30px;
		width: 60px;
		height: 75px;
		background: rgba(20, 20, 20, .1);
		box-shadow: 0px 0 20px 35px rgba(20,20,20,.1);
		border-radius: 30px / 40px;
	}
}
#ballWrapper {
	transform: scale(1);
	transition: all 5s linear 0s;
}

#ballWrapper:active {
	transform: scale(0);
}
