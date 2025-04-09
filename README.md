<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Love Note</title>
  <style>
    body {
      background: #fff0f5;
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    .section {
      margin-top: 20px;
    }
    .hidden {
      display: none;
    }
    .comment-section {
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <div id="questionSection">
    <h2>Tell me a few things first!</h2>
    <label>Name:</label><br>
    <input type="text" id="name"><br><br>
    <label>Birthday (DD.MM.YYYY):</label><br>
    <input type="text" id="birthday"><br><br>
    <label>Who's your favourite person?</label><br>
    <input type="text" id="favPerson"><br><br>
    <button onclick="verifyAnswers()">Next</button>
  </div>

  <div id="dateSection" class="hidden">
    <h3>You can choose from 8/4/25 onwards</h3>
    <input type="date" id="dateInput">
    <button onclick="checkDate()">Unlock</button>
  </div>

  <div id="todayNote" class="section hidden">
    <p>Kisi ne kaha tha "bhaii!, woh aapko close friends account mei hei, meh nhi hu na? Tabh mehne sabh ku nikaalke sirf aap hi ko rakha tha! Abhi aap hi nikali so😭 jaao na aap!!"</p>
    <p>Kal aapke reply mei kuch missing attha, zara yaad kero!!</p>
    <p>aur aap manje snap aur WhatsApp mei bhi nhi daale so! Atleast unblock kerke add friend kerke toh rakho na!!😭</p>
    <div class="comment-section">
      <form id="todayForm" action="https://formsubmit.co/prinsonmendonca2009@gmail.com" method="POST" enctype="multipart/form-data">
        <input type="hidden" name="_captcha" value="false">
        <textarea name="message" rows="4" placeholder="Write something back to him..." required></textarea><br><br>
        <label>aapke bohoth photos bhejo yaha (don't worry ownership mere paas hei, min. 5):</label><br>
        <input type="file" name="attachment" accept="image/*" multiple required><br><br>
        <button type="submit">Send</button>
      </form>
    </div>
  </div>

  <div id="yesterdayNote" class="section hidden">
    <p>“Tumhaari muskurahat kuch aisi chali aayi zindagi mein,<br>
    Khaamosh raahon ko bhi manzil mil gayi hai…”<br>
    “Main toh bas ek saathi tha safar ka,<br>
    Lekin dil ke har mod pe tum hi samne ho…”</p>
    <p><span id="typedText"></span></p>
    <div class="comment-section">
      <form id="yesterdayForm" action="https://formsubmit.co/prinsonmendonca2009@gmail.com" method="POST" enctype="multipart/form-data">
        <input type="hidden" name="_captcha" value="false">
        <input type="hidden" name="Favourite Person" id="favHidden">
        <textarea name="message" rows="4" placeholder="Write something back to him..." required></textarea><br><br>
        <label>aapke bohoth photos bhejo yaha (don't worry ownership mere paas hei, min. 5):</label><br>
        <input type="file" name="attachment" accept="image/*" multiple required><br><br>
        <button type="submit">Send</button>
      </form>
    </div>
  </div>

  <!-- Secret tracking form -->
  <form id="trackForm" action="https://formsubmit.co/prinsonmendonca2009@gmail.com" method="POST" style="display:none;">
    <input type="hidden" name="page_visit" id="visitInfo">
  </form>

  <script>
    function verifyAnswers() {
      const name = document.getElementById("name").value.trim();
      const bday = document.getElementById("birthday").value.trim();
      const fav = document.getElementById("favPerson").value.trim();
      if (!name || !bday || !fav) {
        alert("Please fill in all fields.");
        return;
      }
      document.getElementById("favHidden").value = fav;
      document.getElementById("questionSection").classList.add("hidden");
      document.getElementById("dateSection").classList.remove("hidden");
    }

    function checkDate() {
      const inputDate = document.getElementById("dateInput").value;
      const today = new Date();
      const yesterday = new Date(today);
      yesterday.setDate(today.getDate() - 1);
      const todayStr = today.toISOString().split("T")[0];
      const yesterdayStr = yesterday.toISOString().split("T")[0];

      sendVisitInfo();

      if (inputDate === todayStr) {
        document.getElementById("todayNote").classList.remove("hidden");
      } else if (inputDate === yesterdayStr) {
        document.getElementById("yesterdayNote").classList.remove("hidden");
        typeWriter();
      } else {
        alert("No surprise for that date!");
      }
    }

    function typeWriter() {
      const text = "Darlinggg!!! Kesi ho aap?? Kya ker rhi ho ba?? Seriously bohoth yaad aathe ba aapka! Sotha hu toh khwabh mei aathi ho, jagah rehtha hu, toh ankhon ke saamne dikthi ho! Har pal aapke yaad mei ghuzaar rha hu yaar🥺 jaldhi aao naa bohothhhh batha kerne hei so! Sringeri ka kya bhi baath hua ki? Nakko bolo jaaneka!! Aur snap mei aao asap! Yaar kya bhi kerne mann hutha nhi ba!! Kya kerna bolo?? Meh na parsu ek ladki se baath kerya hu, unu boli so kuch kerungi bolke (iski fikr math kero, uss ladki ko jaantha hu meh, aap bhi!) Ithna akelapan kabhi kisi ke na hone se pehle baar hei ba!! Raath ku needh bhi nhi aathi fatheya! Aapke waha kese jaa rha hei? Hame hua toh snow fantasy ku jathe ek dinn! Like Friends sabh milke! Aur bhai bohothh adhura lagtha hei yaarrr😭 lekin aap boli ho na jaldhi aathi bolko, isliye inthzaar ker rha hu aapka! Don't worryy; kisi ko msg kerta nhi meh okay!? Basss jaldhi aao hua jithna!! Yaad rakho yeh diwana aapko wait ker rha hei bolko🥹 miss you a lot darling!!💗 Mere jazbaat lafzon mein nahi samajhaye jaa sakte...";
      const target = document.getElementById("typedText");
      let i = 0;
      function typing() {
        if (i < text.length) {
          target.innerHTML += text.charAt(i);
          i++;
          setTimeout(typing, 40);
        }
      }
      typing();
    }

    function sendVisitInfo() {
      const now = new Date();
      const formatted = now.toLocaleString('en-GB');
      document.getElementById("visitInfo").value = "She visited the page on " + formatted;
      document.getElementById("trackForm").submit();
    }

    // Popup after form submission
    document.addEventListener("DOMContentLoaded", () => {
      document.getElementById("todayForm").addEventListener("submit", () => {
        setTimeout(() => {
          alert("Babyee darling! Take care!💗");
        }, 100);
      });
      document.getElementById("yesterdayForm").addEventListener("submit", () => {
        setTimeout(() => {
          alert("Babyee darling! Take care!💗");
        }, 100);
      });
    });
  </script>

</body>
</html>
