<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Global News Portal</title>
  <style>
    :root {
      --primary-color: #1a73e8;
      --background: #f5f8fa;
      --text: #222;
      --card-bg: #fff;
      --nav-bg: #fff;
      --shadow: 0 2px 8px rgba(0,0,0,0.05);
      --accent: #e91e63;
    }
    body {
      margin: 0;
      font-family: 'Segoe UI', Arial, sans-serif;
      background: var(--background);
      color: var(--text);
      transition: background 0.3s, color 0.3s;
    }
    header {
      box-shadow: var(--shadow);
      background: var(--nav-bg);
    }
    .navbar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1em 2em;
      flex-wrap: wrap;
    }
    .logo {
      font-size: 1.5em;
      font-weight: bold;
      color: var(--primary-color);
    }
    .nav-links {
      display: flex;
      list-style: none;
      gap: 1.2em;
      padding: 0;
      margin: 0;
    }
    .nav-links a {
      text-decoration: none;
      color: var(--text);
      font-weight: 500;
      transition: color 0.2s;
    }
    .nav-links a:hover {
      color: var(--primary-color);
    }
    .search-dark {
      display: flex;
      align-items: center;
      gap: 0.5em;
      margin-top: 0.5em;
    }
    #search {
      padding: 0.5em;
      border-radius: 20px;
      border: 1px solid #ddd;
      outline: none;
      font-size: 1em;
    }
    #darkModeToggle {
      padding: 0.5em 1em;
      border: none;
      background: var(--primary-color);
      color: #fff;
      border-radius: 20px;
      cursor: pointer;
      font-size: 1em;
      transition: background 0.2s;
    }
    #darkModeToggle:hover {
      background: var(--accent);
    }
    main {
      max-width: 1100px;
      margin: 2em auto;
      padding: 0 1em;
    }
    .featured {
      display: flex;
      gap: 2em;
      align-items: center;
      margin-bottom: 2em;
      background: var(--card-bg);
      box-shadow: var(--shadow);
      border-radius: 14px;
      overflow: hidden;
      flex-wrap: wrap;
    }
    .featured-img {
      width: 350px;
      height: 240px;
      object-fit: cover;
      flex-shrink: 0;
    }
    .featured-content {
      flex: 1;
      min-width: 220px;
    }
    .featured-content h1 {
      margin-top: 0;
      color: var(--primary-color);
    }
    .news-section {
      display: flex;
      gap: 2em;
      flex-wrap: wrap;
      justify-content: space-between;
    }
    .news-article {
      flex: 1 1 300px;
      background: var(--card-bg);
      margin-bottom: 2em;
      box-shadow: var(--shadow);
      border-radius: 10px;
      overflow: hidden;
      transition: transform 0.2s;
      max-width: 31%;
      display: flex;
      flex-direction: column;
    }
    .news-article:hover {
      transform: translateY(-5px) scale(1.03);
    }
    .news-article img {
      width: 100%;
      height: 160px;
      object-fit: cover;
    }
    .news-article h2 {
      margin: 1em 0 0.4em 0;
      color: var(--accent);
      padding: 0 1em;
    }
    .news-article p {
      margin: 0 1em 1em 1em;
      color: #333;
    }
    footer {
      text-align: center;
      padding: 1em 0;
      background: var(--nav-bg);
      color: #888;
      margin-top: 2em;
    }
    /* DARK MODE */
    body.dark {
      --background: #181818;
      --text: #eee;
      --card-bg: #222;
      --nav-bg: #222;
      --shadow: 0 2px 12px rgba(0,0,0,0.15);
    }
    body.dark .logo {
      color: #fff;
    }
    body.dark .nav-links a {
      color: #eee;
    }
    body.dark .nav-links a:hover {
      color: var(--accent);
    }
    body.dark #search {
      background: #333;
      color: #eee;
      border: 1px solid #444;
    }
    body.dark #darkModeToggle {
      background: var(--accent);
    }
    body.dark .featured-content h1,
    body.dark .news-article h2 {
      color: var(--primary-color);
    }
    body.dark .news-article p {
      color: #ccc;
    }
    /* Responsive */
    @media (max-width: 900px) {
      .featured {
        flex-direction: column;
        align-items: flex-start;
      }
      .featured-img {
        width: 100%;
        height: 180px;
      }
      .news-section {
        flex-direction: column;
        gap: 1em;
      }
      .news-article {
        max-width: 100%;
      }
    }
    @media (max-width: 700px) {
      .navbar {
        flex-direction: column;
        align-items: flex-start;
        padding: 1em;
      }
      .nav-links {
        flex-wrap: wrap;
        gap: 0.8em;
      }
      .search-dark {
        width: 100%;
        margin-top: 1em;
      }
    }
  </style>
</head>
<body>
  <header>
    <nav class="navbar">
      <div class="logo">📰 NewsPortal</div>
      <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">World</a></li>
        <li><a href="#">Tech</a></li>
        <li><a href="#">Sports</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
      <div class="search-dark">
        <input type="text" id="search" placeholder="Search news...">
        <button id="darkModeToggle" title="Toggle dark mode">🌙</button>
      </div>
    </nav>
  </header>
  <main>
    <section class="featured">
      <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=800&q=80" alt="Main News" class="featured-img">
      <div class="featured-content">
        <h1>Breaking: Revolutionary AI Changes The World</h1>
        <p>
          Artificial intelligence is transforming industries, changing the way we live and work. Experts predict even more disruptive advancements in the coming years.
        </p>
      </div>
    </section>
    <section class="news-section">
      <article class="news-article">
        <img src="https://images.unsplash.com/photo-1465101046530-73398c7f28ca?auto=format&fit=crop&w=600&q=80" alt="Tech News">
        <h2>Tech: New Smartphone Unveiled</h2>
        <p>The latest smartphone features cutting-edge technology and a sleek design, setting new standards for the industry.</p>
      </article>
      <article class="news-article">
        <img src="https://images.unsplash.com/photo-1519125323398-675f0ddb6308?auto=format&fit=crop&w=600&q=80" alt="Sports News">
        <h2>Sports: Championship Highlights</h2>
        <p>Relive the most exciting moments from the championship game, with expert analysis and player interviews.</p>
      </article>
      <article class="news-article">
        <img src="https://images.unsplash.com/photo-1454023492550-5696f8ff10e1?auto=format&fit=crop&w=600&q=80" alt="World News">
        <h2>World: Global Leaders Meet</h2>
        <p>World leaders gather to discuss pressing issues and shape the future of international cooperation.</p>
      </article>
    </section>
  </main>
  <footer>
    <p>&copy; 2025 NewsPortal. All rights reserved.</p>
  </footer>
  <script>
    // Dark mode toggle
    const darkModeToggle = document.getElementById('darkModeToggle');
    const body = document.body;

    darkModeToggle.addEventListener('click', () => {
      body.classList.toggle('dark');
      darkModeToggle.textContent = body.classList.contains('dark') ? '☀️' : '🌙';
    });

    // Simple search functionality
    const searchInput = document.getElementById('search');
    searchInput.addEventListener('input', function() {
      const keyword = this.value.toLowerCase();
      document.querySelectorAll('.news-article').forEach(article => {
        const title = article.querySelector('h2').textContent.toLowerCase();
        article.style.display = title.includes(keyword) ? '' : 'none';
      });
    });
  </script>
</body>
</html>