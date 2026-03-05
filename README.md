<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Kiểm tra dự thưởng</title>

<style>

body{
font-family:Arial;
background:#f2f2f2;
text-align:center;
}

.box{
background:white;
width:420px;
padding:35px;
margin:120px auto;
box-shadow:0 0 15px rgba(0,0,0,0.2);
border-radius:10px;
}

input{
width:90%;
padding:12px;
margin:8px;
font-size:15px;
}

button{
background:#d40000;
color:white;
border:none;
padding:14px 30px;
font-size:16px;
cursor:pointer;
margin-top:10px;
}

button:hover{
background:#b30000;
}

#ketqua{
margin-top:25px;
font-size:22px;
font-weight:bold;
}

.loading{
font-size:18px;
color:#666;
}

.win{
color:#d40000;
}

</style>

</head>

<body>

<div class="box">

<h2>Kiểm tra điều kiện dự thưởng</h2>

<input placeholder="Số VIN xe"><br>
<input placeholder="Số điện thoại mua xe"><br>
<input placeholder="Email nhận kết quả"><br>

<button onclick="quay()">KIỂM TRA</button>

<div id="ketqua"></div>

</div>

<script>

function quay(){

var ketqua = document.getElementById("ketqua");

ketqua.innerHTML = "<div class='loading'>Đang kiểm tra mã dự thưởng...</div>";

setTimeout(function(){

var random = Math.random();

if(random < 0.01){

ketqua.innerHTML = "<span class='win'>🎉 CHÚC MỪNG!<br>Bạn trúng Ô TÔ VINFAST VF3</span>";
phaohoa();

}

else if(random < 0.08){

ketqua.innerHTML = "<span class='win'>🎉 Chúc mừng!<br>Bạn trúng XE MÁY ĐIỆN VINFAST</span>";

}

else{

ketqua.innerHTML = "Rất tiếc! Mã dự thưởng chưa trúng. Chúc bạn may mắn lần sau.";

}

},3000);

}

function phaohoa(){

for(let i=0;i<40;i++){

let confetti=document.createElement("div");

confetti.style.position="fixed";
confetti.style.width="10px";
confetti.style.height="10px";
confetti.style.background="red";
confetti.style.top="0";
confetti.style.left=Math.random()*window.innerWidth+"px";
confetti.style.opacity="0.8";
confetti.style.transform="rotate("+Math.random()*360+"deg)";
confetti.style.transition="top 2s linear";

document.body.appendChild(confetti);

setTimeout(()=>{
confetti.style.top="100%";
},50);

setTimeout(()=>{
confetti.remove();
},2000);

}

}

</script>

</body>
</html>
