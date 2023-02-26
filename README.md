# AnthonyR2706.github.io
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <title>To Do List</title>
    <style>
    	body{
        	left: 10px;
        }
    	ul{
       	margin: 0;
        padding: 0;
      }
       ul li {
        cursor: pointer;
        padding: 10px;
        border: 1px solid black;
        margin-left: 1%;
        margin-right: 1%;
        background: #f0f0f0;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        }
      ul li:hover{
        background: #b5b5b5 !important; 
      }
      ul li.finished{
        background: #8a8a8a !important;
        color: white;
        text-decoration: line-through
      }
      .header {
       	background-color: #aaaaaa;
        padding-left: 10px;
      	margin-left: 1%;
        margin-right: 1%;
      }
      .header:after {
        content: "";
        display: table;
        clear: both;
      }
      input{
        margin-left: 1%;
        border: 1px solid black;
        width: 74%;
        padding: 10px;
        float: left;
      }
      .dateInput{
	cursor: pointer;
        width: 9%;
        margin-left: 0;
      }
      .button{
        cursor: pointer;
        border: 1px solid black;
        background: #f0f0f0;
        padding: 10px;
        width: 7%;
        float: left;
        text-align: center;
      }
      .button:hover{
        background: #d6d6d6;
      }
      .close {
        position: absolute;
        right: 1%;
        padding-right: 1%;
        padding-left: 1%;
        padding-bottom: 10px;
        padding-top: 10px;
        margin-top: -10px;
      }
      .close:hover{
        background: red;
        color: white;
      }
      .custom-select{
        border: 1px solid black;
        background: #f0f0f0;
        padding: 8px;
        width: 8%;
        float: left;
        text-align: center;
	margin-right: 1%;
      }
    </style>
  </head>
  <body>
  	<div class = "header">
    	<h1>To Do List</h1>
    </div>
    <ul style="list-style-type:none;" id = "myUL">
		  <li>Coding</li>
      <li>Check</li>
    </ul>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    <input type="text" id="input" placeholder="Task...">
    <input type="date" id="date" class="dateInput" placeholder="Due Date">
    <span onclick="newItem()" class="button">Add</span>
    <div class="custom-select"  style="width:8%;">
      <select id="colorInput">
        <option value="0">Color</option>
        <option value="1">Green</option>
        <option value="2">Yellow</option>
        <option value="3">Red</option>
        <option value="3">Grey</option>
      </select>
    </div>
  </body>
    
    <script>   
      function newItem() {
        var li = document.createElement("li");
        var inputValue = document.getElementById("input").value;
        var dateValue = document.getElementById("date").value;
        var colorV = document.getElementById("colorInput");
        var colorValue = colorV.options[colorV.selectedIndex].value;
        console.log(inputValue + colorValue);
        if(dateValue != ""){
          var t = document.createTextNode(inputValue + " Due: " + dateValue);
        } else {
          var t = document.createTextNode(inputValue); 
        }
        switch(colorValue){
          case "1":
            li.style.background = "rgb(157, 252, 179)";
            break;
          case "2":
            li.style.background = "rgb(249, 252, 157)";
            break;
          case "3":
            li.style.background = "rgb(252, 157, 157)";
            break;
          default:
            li.style.background = "rgb(240, 240, 240)";
        }
        li.appendChild(t);
        if (inputValue.replace(/\s/g, '').length) {
          document.getElementById("myUL").appendChild(li);
        }
        document.getElementById("input").value = "";
        var span = document.createElement("SPAN");
        var txt = document.createTextNode("X");
        span.className = "close";
        span.appendChild(txt);
        li.appendChild(span);
        for (i = 0; i < close.length; i++) {
          close[i].onclick = function() {
            var div = this.parentElement;
            div.style.display = "none";
          }
        }
      }
      var list = document.querySelector('ul');
      list.addEventListener('click', function(ev){
        if (ev.target.tagName === 'LI') {
          var click = ev.target.classList.toggle('finished');
          if(click){
            var audio = document.getElementById("audio");
            audio.play();
          }

        }
      }, false);
      
      var myNodelist = document.getElementsByTagName("LI");
      var i;
      for (i = 0; i < myNodelist.length; i++) {
        var span = document.createElement("SPAN");
        var txt = document.createTextNode("X");
        span.className = "close";
        span.appendChild(txt);
        myNodelist[i].appendChild(span);
      }
      
      var close = document.getElementsByClassName("close");
      var i;
      for (i = 0; i < close.length; i++) {
        close[i].onclick = function() {
          var div = this.parentElement;
          div.style.display = "none";
        }
      }  
    </script>
    <audio id="audio" src="https://drive.google.com/uc?export=download&id=1EdGa-o6ZBNVPDygygOnDsXwxaHnyEDAm" type="audio/mp3"></audio>
</html>
