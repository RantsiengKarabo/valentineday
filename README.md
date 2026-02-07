@@ -24,25 +24,52 @@

[<img align="left" alt="JoshMadakor | YouTube" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/youtube.svg" />][youtube]
[<img align="left" alt="JoshMadakor | Facebook" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/facebook.svg" />][facebook]
[<img align="left" alt="JoshMadakor | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />][linkedin]
[<img align="left" alt="JoshMadakor | Instagram" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/instagram.svg" />][instagram]

[facebook]: https://www.facebook.com/karabo.rantsieng
[youtube]: https://www.youtube.com/c/joshmadakorf
[instagram]: https://www.instagram.com/kb_rantsieng98/
[linkedin]: https://www.linkedin.com/in/karabo-rantsieng/

<!--
**joshmadakor1/joshmadakor1** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

---

## 💘 Publish and share your Valentine website

This repo now includes a GitHub Pages workflow at `.github/workflows/deploy-pages.yml`.

### 1) Push this branch to GitHub
```bash
git push origin work
```

### 2) Enable GitHub Pages once
- Open your repository on GitHub.
- Go to **Settings → Pages**.
- Under **Build and deployment**, set **Source** to **GitHub Actions**.

### 3) Get your link
After the workflow finishes, your site link will be:

- `https://<your-github-username>.github.io/RantsiengKarabo/`

For your username, that should likely be:

- `https://rantsiengkarabo.github.io/RantsiengKarabo/`

Share that link with Tshegofatso ❤️
index.html
index.html
New
+169
-0

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Be My Valentine, Tshegofatso?</title>
  <style>
    :root {
      --red: #c1121f;
      --soft-red: #ff4d6d;
      --white: #fff;
      --pink: #ffe5ec;
      --shadow: rgba(193, 18, 31, 0.25);
    }

    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      display: grid;
      place-items: center;
      font-family: "Poppins", "Segoe UI", sans-serif;
      background: radial-gradient(circle at top, #fff 20%, #ffe5ec 100%);
      color: var(--red);
      overflow: hidden;
    }

    .hearts {
      position: fixed;
      inset: 0;
      pointer-events: none;
      opacity: 0.25;
      background-image:
        radial-gradient(circle at 10% 20%, var(--soft-red) 0 1rem, transparent 1.1rem),
        radial-gradient(circle at 85% 10%, var(--red) 0 0.8rem, transparent 0.9rem),
        radial-gradient(circle at 70% 80%, var(--soft-red) 0 1.2rem, transparent 1.3rem),
        radial-gradient(circle at 20% 75%, var(--red) 0 0.7rem, transparent 0.8rem);
      animation: float 10s linear infinite alternate;
    }

    @keyframes float {
      from { transform: translateY(0); }
      to { transform: translateY(-16px); }
    }

    .card {
      width: min(92vw, 700px);
      background: var(--white);
      border: 3px solid var(--red);
      border-radius: 24px;
      box-shadow: 0 20px 60px var(--shadow);
      padding: clamp(1.5rem, 4vw, 3rem);
      text-align: center;
      position: relative;
      z-index: 1;
    }

    h1 {
      margin: 0;
      font-size: clamp(1.8rem, 5vw, 3rem);
      line-height: 1.2;
      color: var(--red);
    }

    .name {
      color: var(--soft-red);
      font-weight: 700;
      text-decoration: underline wavy var(--red);
      text-underline-offset: 0.4rem;
    }

    p {
      margin: 1rem auto;
      font-size: clamp(1rem, 2.4vw, 1.25rem);
      max-width: 36ch;
    }

    .question {
      margin-top: 1.5rem;
      font-size: clamp(1.4rem, 4vw, 2rem);
      font-weight: 700;
    }

    .buttons {
      margin-top: 1.5rem;
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
    }

    button {
      border: none;
      border-radius: 999px;
      font-size: 1rem;
      padding: 0.8rem 1.5rem;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .yes {
      background: var(--red);
      color: var(--white);
      box-shadow: 0 8px 24px var(--shadow);
    }

    .no {
      background: #fff0f3;
      color: var(--red);
      border: 2px solid var(--red);
    }

    button:hover {
      transform: translateY(-2px) scale(1.02);
    }

    .footer {
      margin-top: 1.8rem;
      font-style: italic;
      font-weight: 600;
      color: #8b0000;
    }

    .message {
      min-height: 2rem;
      font-weight: 700;
      color: var(--soft-red);
      margin-top: 1rem;
    }
  </style>
</head>
<body>
  <div class="hearts" aria-hidden="true"></div>

  <main class="card" role="main">
    <h1>Hi <span class="name">Tshegofatso</span> 💖</h1>
    <p>
      Every day with you feels warmer, brighter, and full of love.
      You make my world better just by being in it.
    </p>

    <div class="question">Can you be my Valentine? ❤️</div>

    <div class="buttons">
      <button class="yes" id="yesBtn">Yes, of course! 💘</button>
      <button class="no" id="noBtn">I need convincing 😄</button>
    </div>

    <div class="message" id="message" aria-live="polite"></div>

    <div class="footer">Forever yours, Karabo 💌</div>
  </main>

  <script>
    const message = document.getElementById('message');
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');

    yesBtn.addEventListener('click', () => {
      message.textContent = 'Yay! This made my heart smile. I love you, Tshegofatso! 🥰';
    });

    noBtn.addEventListener('click', () => {
      message.textContent = 'Roses are red, violets are blue, no one compares to amazing you. 🌹';
    });
  </script>
</body>
</html>
