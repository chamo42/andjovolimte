!DOCTYPE html>
<html lang="sr">
<head>
  <meta charset="UTF-8">
  <title>Za Moju Andju ❤️</title>
  <style>
    body {
      font-family: sans-serif;
      background: linear-gradient(to right, #ffe6f0, #ffe0f7);
      margin: 0;
      padding: 0;
      text-align: center;
      overflow-x: hidden;
      overflow-y: auto;
    }

    header {
      background-color: #ffb6c1;
      color: white;
      padding: 2rem;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }

    .slider-container {
      position: relative;
      width: 90%;
      max-width: 800px;
      margin: 2rem auto;
      overflow: hidden;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    .slider-images {
      display: flex;
      transition: transform 0.5s ease-in-out;
      width: 100%;
    }

    .slider-images img {
      width: 100%;
      flex-shrink: 0;
    }

    .slider-buttons {
      position: absolute;
      top: 50%;
      width: 100%;
      display: flex;
      justify-content: space-between;
      transform: translateY(-50%);
    }

    .slider-buttons button {
      background-color: rgba(255, 182, 193, 0.8);
      border: none;
      padding: 0.5rem 1rem;
      cursor: pointer;
      font-size: 1.2rem;
      border-radius: 8px;
      transition: background-color 0.3s;
    }

    .slider-buttons button:hover {
      background-color: rgba(255, 105, 180, 0.9);
    }

    .hearts {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 10s linear infinite;
    }

    .heart::before, .heart::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      top: 0;
      left: -10px;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Za Najlepsu Na Svetu ❤️</h1>
  </header>

  <p>Ovo je mali znak paznje da znas koliko te volim</p>

  <!-- DUGME ZA LJUBAVNO PISMO -->
  <button onclick="openLetter()" style="margin-top: 1rem; padding: 0.8rem 1.2rem; font-size: 1rem; background-color: #ffb6c1; border: none; border-radius: 10px; cursor: pointer;">
    💌 Klikni ovde da procitas moje pismo za tebe
  </button>

  <!-- PROZOR SA LJUBAVNIM PISMOM -->
  <div id="letterPopup" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.6); z-index:10; justify-content:center; align-items:center;">
    <div style="background:white; padding:2rem; max-width:600px; border-radius:15px; text-align:left; box-shadow: 0 4px 12px rgba(0,0,0,0.3); position:relative;">
      <h2 style="text-align:center;">Za tebe Andjo moja ❤️</h2>
      <p style="line-height:1.6;">
       Od svih dana u zivotu 15 mart je dan koji cu pamtiti zauvek  
        jer tog dana je moje srce pocelo da pripada tebi. Tvoje oci su mi pokazale mir.Tvoj osmeh me uvek podseti da je zivot lep.Tvoje prisustvo me uci sta znaci prava ljubav.Volim sve na tebi tvoju dobrotu tvoju iskrenost tvoju toplinu  
        Volim kad me pogledas kao da sam ti ceo svet jer Andjo ti si moj ceo svet.Obećavam da cu uvek biti uz tebe da te volim cuvam i podrzavam  
        Ti si moja ljubav moj oslonac i moja buducnost. Hvala ti ya svaki mali znak paznje koji si mi pruzila. Znam da sam ponekad malo naporan sa time ali Volim te najvise na svetu.
      <p style="text-align:right; margin-top:2rem;">Tvoj zauvek ❤️</p>
      <button onclick="closeLetter()" style="margin-top:1rem; background:#ffb6c1; padding:0.5rem 1rem; border:none; border-radius:8px; cursor:pointer;">Zatvori</button>
    </div>
  </div>

  <!-- SLIDER -->
  <div class="slider-container">
    <div class="slider-images" id="slider-images">
      <img src="slika1.jpg" alt="Slika 1">
      <img src="slika2.jpg" alt="Slika 2">
      <img src="slika3.jpg" alt="Slika 3">
      <img src="slika4.jpg" alt="Slika 4">
      <img src="slika5.jpg" alt="Slika 5">
    </div>
    <div class="slider-buttons">
      <button onclick="prevSlide()">⬅</button>
      <button onclick="nextSlide()">➡</button>
    </div>
  </div>

  <!-- SRCA -->
  <div class="hearts" id="hearts"></div>

  <script>
    // Automatski & rucni slajder
    const slider = document.getElementById('slider-images');
    const images = slider.getElementsByTagName('img');
    let currentIndex = 0;

    function showSlide(index) {
      slider.style.transform = `translateX(-${index * 100}%)`;
    }

    function nextSlide() {
      currentIndex = (currentIndex + 1) % images.length;
      showSlide(currentIndex);
    }

    function prevSlide() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      showSlide(currentIndex);
    }

    setInterval(nextSlide, 3000); // Automatski na 3 sekunde

    // Ljubavno pismo
    function openLetter() {
      document.getElementById("letterPopup").style.display = "flex";
    }
    function closeLetter() {
      document.getElementById("letterPopup").style.display = "none";
    }

    // Leprsajuca srca
    const heartsContainer = document.getElementById('hearts');
    setInterval(() => {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (5 + Math.random() * 5) + 's';
      heartsContainer.appendChild(heart);
      setTimeout(() => heart.remove(), 10000);
    }, 500);
  </script>
</body>
</html>
