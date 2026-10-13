
<!DOCTYPE html>
<html lang="sw">
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>WiFi Admin</title>
<style>
body{font-family:Arial;background:#edf2f7;padding:15px}
main{max-width:450px;margin:auto}
section{background:white;padding:16px;margin:12px 0;border-radius:12px}
button,select{padding:12px;margin-top:8px}
button{background:#087e8b;color:white;border:0;border-radius:7px}
</style>
<main>
<section style="background:#123b70;color:white">
<h2>WiFi Yangu</h2>
<p>Dashibodi ya msimamizi</p>
</section>
<section>
<h3>Tengeneza vocha</h3>
<select id="p">
<option value="500|Saa 1">Saa 1 - TSh 500</option>
<option value="1000|Saa 3">Saa 3 - TSh 1,000</option>
<option value="2000|Saa 24">Saa 24 - TSh 2,000</option>
</select><br>
<button onclick="add()">Tengeneza vocha</button>
<p id="new">Bado hakuna vocha.</p>
</section>
<section>
<h3>Muhtasari</h3>
<p>Vocha: <b id="n">0</b></p>
<p>Thamani: <b id="s">TSh 0</b></p>
</section>
<section>
<h3>Orodha ya vocha</h3>
<div id="list">Hakuna vocha bado.</div>
</section>
</main>
<script>
let data=[];
function add(){
 let p=document.getElementById('p').value.split('|');
 let v={name:'TEST'+Math.floor(100000+Math.random()*900000),
 price:+p[0],pack:p[1]};
 data.push(v);
 document.getElementById('new').textContent=
 'Vocha: '+v.name+' | '+v.pack;
 document.getElementById('n').textContent=data.length;
 document.getElementById('s').textContent='TSh '+
 data.reduce((a,b)=>a+b.price,0).toLocaleString('en-US');
 document.getElementById('list').innerHTML=data.map(v=>
 '<p>'+v.name+' — '+v.pack+' — TSh '+
 v.price.toLocaleString('en-US')+'</p>').join('');
}
</script>
</html>

