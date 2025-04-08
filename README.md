<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For You, Mi Amor</title>
  <style>
    body {
      background: #ffe6f0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: #333;
      padding: 20px;
      overflow-x: hidden;
    }
    .heart {
      font-size: 3em;
      text-align: center;
      margin-top: 20px;
    }
    .message {
      text-align: center;
      font-size: 1.5em;
      margin-top: 10px;
    }
    .para {
      margin-top: 20px;
      font-size: 1.1em;
      line-height: 1.6em;
      background: #fff0f5;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .comment-box {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      width: 100%;
      text-align: center;
      background: #ffe6f0;
      padding: 10px 0;
      z-index: 1000;
    }
    textarea {
      width: 80%;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      margin-top: 10px;
      padding: 10px 20px;
      border: none;
      background-color: #ff6699;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #ff3366;
    }
    span {
      position: absolute;
      animation: fall linear infinite;
    }
    @keyframes fall {
      to {
        transform: translateY(100vh);
      }
    }
  </style>
</head>
<body>
<audio autoplay loop>
  <source src="Stephen_Sanchez_Until_I_Found_English_Song_Ringtone_(by Fringster.com).mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
<div id="petalContainer"></div>
<script>
  let name = prompt("What is your name?");
  if (!name || !["rufiya", "rufiya banu ahmed"].includes(name.toLowerCase().trim())) {
    document.body.innerHTML = "<h2>Access Denied</h2>";
    throw new Error("Wrong name");
  }
  let bday = prompt("When is your birthday? (DD.MM.YYYY)");
  if (bday.trim() !== "18.11.2008") {
    document.body.innerHTML = "<h2>Access Denied</h2>";
    throw new Error("Wrong birthday");
  }
  let calledName = prompt("What's the name he calls you?");
  if (!calledName || calledName.toLowerCase().trim() !== "darling") {
    document.body.innerHTML = "<h2>Access Denied</h2>";
    throw new Error("Wrong nickname");
  }
  const petalContainer = document.getElementById("petalContainer");
  for (let i = 0; i < 40; i++) {
    let span = document.createElement("span");
    span.innerText = "🌹";
    span.style.left = Math.random() * 100 + "vw";
    span.style.fontSize = (Math.random() * 20 + 10) + "px";
    span.style.animationDuration = (Math.random() * 5 + 5) + "s";
    span.style.animationDelay = Math.random() * 5 + "s";
    petalContainer.appendChild(span);
  }
  document.body.innerHTML += `
    <div class="heart">💗</div>
    <div class="message">Hello darling!💗</div>
    <div class="para">
      “Tumhaari muskurahat kuch aisi chali aayi zindagi mein,<br>
      Khaamosh raahon ko bhi manzil mil gayi hai…”<br>
      “Main toh bas ek saathi tha safar ka,<br>
      Lekin dil ke har mod pe tum hi samne ho…”<br><br>
      <span id="typed-text"></span>
    </div>
    <div class="comment-box">
      <form action="https://formsubmit.co/prinsonmendonca2009@gmail.com" method="POST">
        <input type="hidden" name="_captcha" value="false">
        <textarea name="message" rows="4" placeholder="Write something back to him..." required></textarea><br>
        <button type="submit">Send to Him</button>
      </form>
    </div>
  `;
  const text = `Darlinggg!!! Kesi ho aap?? Kya ker rhi ho ba?? Seriously bohoth yaad aathe ba aapka!  Sotha hu toh khwabh mei aathi ho, jagah rehtha hu, toh ankhon ke saamne dikthi ho!  Har pal aapke yaad mei ghuzaar rha hu yaar🥺 jaldhi aao naa bohothhhh batha kerne hei so!  Sringeri ka kya bhi baath hua ki? Nakko bolo jaaneka!! Aur snap mei aao asap!  Yaar kya bhi kerne mann hutha nhi ba!! Kya kerna bolo?? Meh na parsu ek ladki se baath kerya hu,  unu boli so kuch kerungi bolke (iski fikr math kero, uss ladki ko jaantha hu meh, aap bhi!)  Ithna akelapan kabhi kisi ke na hone se pehle baar hei ba!!  Raath ku needh bhi nhi aathi fatheya! Aapke waha kese jaa rha hei?  Hame hua toh snow fantasy ku jathe ek dinn! Like Friends sabh milke!  Aur bhai bohothh adhura lagtha hei yaarrr😭 lekin aap boli ho na jaldhi aathi bolko,  isliye inthzaar ker rha hu aapka! Don't worryy; kisi ko msg kerta nhi meh okay!?  Basss jaldhi aao hua jithna!! Yaad rakho yeh diwana aapko wait ker rha hei bolko🥹  miss you a lot darling!!💗 Mere jazbaat lafzon mein nahi samajhaye jaa sakte...`;
  const typedText = document.getElementById("typed-text");
  let index = 0;
  function typeWriter() {
    if (index < text.length) {
      typedText.innerHTML += text.charAt(index);
      index++;
      setTimeout(typeWriter, 50);
    }
  }
  setTimeout(typeWriter, 2000);
</script>
</body>
</html>
