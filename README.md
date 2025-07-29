# SF.com

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SF.com - Sports Website</title>
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box;}
    body {font-family: Arial, sans-serif; line-height: 1.6; background: #f4f4f4; color: #333; transition: 0.3s;}
    header {background: #222; color: #fff; padding: 1rem;}
    nav ul {display: flex; gap: 1rem; list-style: none;}
    nav ul li a, button {color: #fff; text-decoration: none; background: none; border: none; cursor: pointer; font-size: 1rem;}
    main {padding: 2rem;}
    h2 {margin-bottom: 1rem;}
    #searchInput {padding: 0.5rem; width: 100%; max-width: 300px; margin-bottom: 1rem;}
    #newsContainer {margin-bottom: 2rem;}
    .gallery {display: flex; gap: 1rem; flex-wrap: wrap;}
    .gallery img {width: 200px; height: auto; border-radius: 8px;}
    form {display: flex; flex-direction: column; gap: 1rem; max-width: 400px;}
    form input, textarea {padding: 0.5rem; border: 1px solid #ccc; border-radius: 4px;}
    form button {padding: 0.5rem; background: #222; color: white; border: none; cursor: pointer;}
    footer {text-align: center; padding: 1rem; background: #222; color: white; margin-top: 2rem;}
    body.dark {background: #111; color: #eee;}
    body.dark header, body.dark footer {background: #000;}
  </style>
</head>
<body>
  <header>
    <h1>SF.com</h1>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#live">Live Scores</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><button onclick="toggleMode()">🌓</button></li>
      </ul>
    </nav>
  </header>

  <main>
    <section id="home">
      <h2>Latest Sports News</h2>
      <input type="text" id="searchInput" placeholder="Search News..." onkeyup="searchNews()">
      <div id="newsContainer"></div>
    </section>

    <section id="live">
      <h2>Live Scores</h2>
      <ul id="liveScores"></ul>
    </section>

    <section id="gallery">
      <h2>Sports Gallery</h2>
      <div class="gallery">
        <img src="https://via.placeholder.com/200" alt="Game 1">
        <img src="https://via.placeholder.com/200" alt="Game 2">
        <img src="https://via.placeholder.com/200" alt="Game 3">
      </div>
    </section>

    <section id="contact">
      <h2>Contact Us</h2>
      <form id="contactForm" onsubmit="submitForm(event)">
        <input type="text" placeholder="Your Name" required>
        <input type="email" placeholder="Your Email" required>
        <textarea placeholder="Your Message" required></textarea>
        <button type="submit">Send</button>
      </form>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 SF.com. All rights reserved.</p>
  </footer>

  <script>
    const news = [
      "Bangladesh beats India in final over thriller!",
      "Cristiano Ronaldo scores 3 in Saudi League",
      "Bangladesh to host ICC World Cup Qualifiers",
      "Lionel Messi joins Inter Miami",
      "Shakib Al Hasan retires from T20s"
    ];

    const scores = [
      "Bangladesh 254/6 vs India",
      "Argentina 2 - 1 Brazil",
      "England 3 - 0 Australia",
      "Dhaka Dynamos 89/3 vs Sylhet Kings"
    ];

    function loadNews() {
      const container = document.getElementById("newsContainer");
      container.innerHTML = "";
      news.forEach(item => {
        const p = document.createElement("p");
        p.textContent = item;
        container.appendChild(p);
      });
    }

    function searchNews() {
      const query = document.getElementById("searchInput").value.toLowerCase();
      const container = document.getElementById("newsContainer");
      container.innerHTML = "";
      news.filter(item => item.toLowerCase().includes(query))
          .forEach(item => {
              const p = document.createElement("p");
              p.textContent = item;
              container.appendChild(p);
          });
    }

    function loadScores() {
      const list = document.getElementById("liveScores");
      scores.forEach(score => {
        const li = document.createElement("li");
        li.textContent = score;
        list.appendChild(li);
      });
    }

    function toggleMode() {
      document.body.classList.toggle("dark");
    }

    function submitForm(e) {
      e.preventDefault();
      alert("Thanks! Your message has been sent.");
      document.getElementById("contactForm").reset();
    }

    loadNews();
    loadScores();
  </script>
</body>
</html>


