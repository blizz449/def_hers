<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#100d13" />
  <title>Bree & Brian — Our Story</title>

  <style>
    :root {
      color-scheme: dark;
      --background: #100d13;
      --panel: rgba(31, 24, 34, 0.78);
      --text: #f7f0eb;
      --muted: #b7a9b5;
      --rose: #e8a4b4;
      --gold: #e9c99c;
      --line: rgba(255, 255, 255, 0.12);
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      min-height: 100vh;
      overflow-x: hidden;
      background:
        radial-gradient(ellipse at 50% 0%, rgba(107, 57, 88, 0.25), transparent 48%),
        radial-gradient(ellipse at 90% 60%, rgba(71, 52, 89, 0.16), transparent 40%),
        var(--background);
      color: var(--text);
      font-family: Georgia, "Times New Roman", serif;
    }

    body.calm *,
    body.calm *::before,
    body.calm *::after {
      animation-duration: 0.01ms !important;
      animation-iteration-count: 1 !important;
      scroll-behavior: auto !important;
    }

    #stars {
      position: fixed;
      inset: 0;
      z-index: -1;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }

    .page {
      width: min(100% - 32px, 1040px);
      margin: 0 auto;
    }

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 26px 0;
      color: var(--muted);
      font-family: Arial, sans-serif;
      font-size: 0.78rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .brand {
      color: var(--rose);
      letter-spacing: 0.2em;
    }

    button,
    input {
      font: inherit;
    }

    .quiet-button {
      border: 1px solid var(--line);
      border-radius: 999px;
      padding: 9px 14px;
      background: rgba(255, 255, 255, 0.03);
      color: var(--muted);
      cursor: pointer;
      transition: border-color 180ms ease, color 180ms ease, background 180ms ease;
    }

    .quiet-button:hover {
      border-color: var(--rose);
      color: var(--text);
      background: rgba(232, 164, 180, 0.08);
    }

    main {
      padding-bottom: 48px;
    }

    .hero {
      min-height: 390px;
      display: grid;
      place-items: center;
      text-align: center;
      padding: 55px 16px 36px;
    }

    .eyebrow {
      margin: 0 0 17px;
      color: var(--gold);
      font-family: Arial, sans-serif;
      font-size: 0.76rem;
      letter-spacing: 0.28em;
      text-transform: uppercase;
    }

    h1 {
      margin: 0;
      font-size: clamp(3rem, 9vw, 6.6rem);
      font-weight: 400;
      letter-spacing: -0.055em;
      line-height: 0.98;
    }

    h1 span {
      display: block;
      margin: 10px 0;
      color: var(--rose);
      font-size: 0.43em;
      font-style: italic;
      letter-spacing: 0;
    }

    .hero-caption {
      max-width: 520px;
      margin: 24px auto 0;
      color: var(--muted);
      font-size: clamp(1rem, 2.5vw, 1.18rem);
      line-height: 1.8;
    }

    .heart {
      display: inline-block;
      color: var(--rose);
      animation: heartbeat 2s ease-in-out infinite;
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      12% { transform: scale(1.16); }
      24% { transform: scale(1); }
      36% { transform: scale(1.1); }
    }

    .counter-card {
      position: relative;
      overflow: hidden;
      padding: clamp(24px, 5vw, 48px);
      border: 1px solid var(--line);
      border-radius: 24px;
      background: linear-gradient(145deg, rgba(47, 34, 48, 0.84), var(--panel));
      box-shadow: 0 24px 80px rgba(0, 0, 0, 0.25);
      text-align: center;
    }

    .counter-card::before {
      position: absolute;
      top: -110px;
      left: 50%;
      width: 320px;
      height: 220px;
      border-radius: 50%;
      background: rgba(232, 164, 180, 0.1);
      content: "";
      filter: blur(40px);
      transform: translateX(-50%);
      pointer-events: none;
    }

    .counter-title {
      position: relative;
      margin: 0 0 8px;
      color: var(--muted);
      font-size: 1rem;
      font-style: italic;
    }

    .days {
      position: relative;
      margin: 0;
      color: var(--rose);
      font-size: clamp(4rem, 13vw, 8rem);
      line-height: 1;
    }

    .days-label {
      position: relative;
      margin: 8px 0 30px;
      color: var(--gold);
      font-family: Arial, sans-serif;
      font-size: 0.78rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
    }

    .time-grid {
      position: relative;
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 12px;
      max-width: 760px;
      margin: 0 auto;
    }

    .time-unit {
      padding: 18px 8px;
      border: 1px solid var(--line);
      border-radius: 14px;
      background: rgba(7, 6, 9, 0.28);
    }

    .time-value {
      display: block;
      color: var(--text);
      font-family: Arial, sans-serif;
      font-size: clamp(1.3rem, 5vw, 2.4rem);
      font-variant-numeric: tabular-nums;
      letter-spacing: 0.03em;
    }

    .time-label {
      display: block;
      margin-top: 7px;
      color: var(--muted);
      font-family: Arial, sans-serif;
      font-size: 0.68rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }

    .microseconds {
      margin: 17px 0 0;
      color: var(--muted);
      font-family: Arial, sans-serif;
      font-size: 0.82rem;
      font-variant-numeric: tabular-nums;
      letter-spacing: 0.04em;
    }

    .microseconds strong {
      color: var(--gold);
      font-weight: 400;
    }

    .precision-note {
      margin: 9px 0 0;
      color: #8f8290;
      font-family: Arial, sans-serif;
      font-size: 0.7rem;
    }

    .date-control {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      gap: 10px;
      margin-top: 24px;
      color: var(--muted);
      font-family: Arial, sans-serif;
      font-size: 0.84rem;
    }

    .date-control input {
      border: 1px solid var(--line);
      border-radius: 8px;
      padding: 8px 10px;
      background: rgba(0, 0, 0, 0.22);
      color: var(--text);
    }

    .story-section {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      margin-top: 28px;
    }

    .story-card,
    .timeline-card {
      padding: clamp(22px, 4vw, 34px);
      border: 1px solid var(--line);
      border-radius: 20px;
      background: rgba(24, 19, 27, 0.72);
    }

    h2 {
      margin: 0 0 14px;
      color: var(--gold);
      font-size: 1.55rem;
      font-weight: 400;
    }

    .story-card p {
      margin: 0;
      color: var(--muted);
      font-size: 1.02rem;
      line-height: 1.9;
    }

    .timeline {
      display: grid;
      gap: 19px;
      margin-top: 23px;
    }

    .moment {
      display: grid;
      grid-template-columns: 16px 1fr;
      gap: 12px;
      align-items: start;
    }

    .moment-dot {
      width: 9px;
      height: 9px;
      margin-top: 7px;
      border: 1px solid var(--rose);
      border-radius: 50%;
      box-shadow: 0 0 12px rgba(232, 164, 180, 0.55);
    }

    .moment strong {
      display: block;
      margin-bottom: 4px;
      color: var(--text);
      font-weight: 400;
    }

    .moment span {
      color: var(--muted);
      font-size: 0.9rem;
      line-height: 1.6;
    }

    .note-area {
      margin-top: 28px;
      padding: clamp(24px, 5vw, 44px);
      border: 1px solid rgba(232, 164, 180, 0.22);
      border-radius: 20px;
      background: linear-gradient(120deg, rgba(67, 39, 57, 0.5), rgba(24, 19, 27, 0.76));
      text-align: center;
    }

    .note-area h2 {
      margin-bottom: 9px;
    }

    .note-area > p {
      margin: 0 auto 20px;
      color: var(--muted);
      line-height: 1.7;
    }

    .primary-button {
      border: 0;
      border-radius: 999px;
      padding: 12px 20px;
      background: linear-gradient(135deg, #e8a4b4, #e9c99c);
      color: #21151d;
      cursor: pointer;
      font-family: Arial, sans-serif;
      font-weight: 700;
      transition: transform 180ms ease, filter 180ms ease;
    }

    .primary-button:hover {
      filter: brightness(1.08);
      transform: translateY(-2px);
    }

    .love-note {
      max-width: 650px;
      margin: 24px auto 0;
      color: var(--text);
      font-size: 1.18rem;
      line-height: 1.9;
    }

    .love-note[hidden] {
      display: none;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin-top: 22px;
    }

    footer {
      padding: 14px 0 34px;
      color: #8f8290;
      font-family: Arial, sans-serif;
      font-size: 0.78rem;
      text-align: center;
    }

    @media (max-width: 680px) {
      .story-section {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 460px) {
      .page {
        width: min(100% - 22px, 1040px);
      }

      header {
        padding: 18px 0;
      }

      .time-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .hero {
        min-height: 320px;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      *,
      *::before,
      *::after {
        scroll-behavior: auto !important;
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
      }
    }
  </style>
</head>

<body>
  <canvas id="stars" aria-hidden="true"></canvas>

  <div class="page">
    <header>
      <div class="brand">Bree &amp; Brian</div>
      <button class="quiet-button" id="motionButton" type="button" aria-pressed="false">
        Reduce motion
      </button>
    </header>

    <main>
      <section class="hero">
        <div>
          <p class="eyebrow">A story written in time</p>
          <h1>
            Bree
            <span>and</span>
            Brian
          </h1>
          <p class="hero-caption">
            One October day, two paths crossed—and every moment since became
            part of a story worth keeping. <span class="heart">♥</span>
          </p>
        </div>
      </section>

      <section class="counter-card" aria-label="Time since Bree and Brian met">
        <p class="counter-title">Since the day our story began</p>
        <p class="days" id="days">0</p>
        <p class="days-label">days together</p>

        <div class="time-grid" aria-live="off">
          <div class="time-unit">
            <span class="time-value" id="hours">00</span>
            <span class="time-label">hours</span>
          </div>
          <div class="time-unit">
            <span class="time-value" id="minutes">00</span>
            <span class="time-label">minutes</span>
          </div>
          <div class="time-unit">
            <span class="time-value" id="seconds">00</span>
            <span class="time-label">seconds</span>
          </div>
          <div class="time-unit">
            <span class="time-value" id="milliseconds">000</span>
            <span class="time-label">milliseconds</span>
          </div>
        </div>

        <p class="microseconds">
          And <strong id="microseconds">000000</strong> microseconds into
          this very second
        </p>
        <p class="precision-note">
          The counter updates live; actual clock precision depends on your device and browser.
        </p>

        <div class="date-control">
          <label for="metDate">Our date:</label>
          <input id="metDate" type="date" value="2026-10-05" />
        </div>
      </section>

      <section class="story-section">
        <article class="story-card">
          <h2>Where it began</h2>
          <p>
            It began on October fifth—not with a promise to know every chapter,
            but with the start of something beautiful. Since then, the little
            moments have been adding up: the conversations, the laughter, and
            the feeling that life is a little brighter with each other in it.
          </p>
        </article>

        <article class="timeline-card">
          <h2>Our little timeline</h2>
          <div class="timeline">
            <div class="moment">
              <span class="moment-dot"></span>
              <div>
                <strong>October 5 — The beginning</strong>
                <span>The day Bree and Brian’s story got its first page.</span>
              </div>
            </div>
            <div class="moment">
              <span class="moment-dot"></span>
              <div>
                <strong>Every day after</strong>
                <span>Another memory, another reason to be grateful.</span>
              </div>
            </div>
            <div class="moment">
              <span class="moment-dot"></span>
              <div>
                <strong>Today — Still choosing this story</strong>
                <span>The next page is waiting to be written together.</span>
              </div>
            </div>
          </div>
        </article>
      </section>

      <section class="note-area">
        <h2>A little note for you</h2>
        <p>Some words are worth opening more than once.</p>
        <button class="primary-button" id="noteButton" type="button">
          Open our note
        </button>

        <p class="love-note" id="loveNote" hidden>
          Bree, meeting you gave an ordinary date a meaning I’ll always carry.
          Thank you for being part of my days and for making this story ours.
          Here’s to every moment we’ve shared, and to all the beautiful ones
          still waiting for us. — Brian
        </p>

        <div class="actions">
          <button class="quiet-button" id="copyButton" type="button">Copy our story</button>
          <button class="quiet-button" id="shareButton" type="button">Share this page</button>
        </div>
      </section>
    </main>

    <footer>
      Made with love for Bree &amp; Brian <span class="heart">♥</span>
    </footer>
  </div>

  <script>
    // Change the default date here too, if you prefer a different starting date.
    const DEFAULT_MET_DATE = "2026-10-05";

    const dateInput = document.getElementById("metDate");
    const dayDisplay = document.getElementById("days");
    const hourDisplay = document.getElementById("hours");
    const minuteDisplay = document.getElementById("minutes");
    const secondDisplay = document.getElementById("seconds");
    const millisecondDisplay = document.getElementById("milliseconds");
    const microsecondDisplay = document.getElementById("microseconds");

    // Parse the date as local time so the chosen calendar day stays consistent.
    function getStartDate() {
      const [year, month, day] = dateInput.value.split("-").map(Number);
      if (!year || !month || !day) return null;
      return new Date(year, month - 1, day, 0, 0, 0, 0);
    }

    function updateCounter() {
      const start = getStartDate();
      if (!start) return;

      // Date.now provides the wall-clock time; performance.now adds a smooth
      // sub-millisecond estimate between wall-clock readings.
      const elapsedMs = Date.now() - start.getTime();
      if (elapsedMs < 0) {
        dayDisplay.textContent = "0";
        hourDisplay.textContent = "00";
        minuteDisplay.textContent = "00";
        secondDisplay.textContent = "00";
        millisecondDisplay.textContent = "000";
        microsecondDisplay.textContent = "000000";
        return;
      }

      const totalSeconds = Math.floor(elapsedMs / 1000);
      const days = Math.floor(totalSeconds / 86400);
      const hours = Math.floor((totalSeconds % 86400) / 3600);
      const minutes = Math.floor((totalSeconds % 3600) / 60);
      const seconds = totalSeconds % 60;
      const milliseconds = Math.floor(elapsedMs % 1000);

      dayDisplay.textContent = days.toLocaleString();
      hourDisplay.textContent = String(hours).padStart(2, "0");
      minuteDisplay.textContent = String(minutes).padStart(2, "0");
      secondDisplay.textContent = String(seconds).padStart(2, "0");
      millisecondDisplay.textContent = String(milliseconds).padStart(3, "0");

      // This displays the millisecond value as six digits of microseconds.
      // Browsers do not provide a reliable, continuously refreshed wall clock
      // with true microsecond accuracy.
      microsecondDisplay.textContent = String(milliseconds * 1000).padStart(6, "0");
    }

    dateInput.value = DEFAULT_MET_DATE;
    dateInput.addEventListener("change", updateCounter);
    updateCounter();
    setInterval(updateCounter, 30);

    document.getElementById("noteButton").addEventListener("click", (event) => {
      const note = document.getElementById("loveNote");
      note.hidden = !note.hidden;
      event.currentTarget.textContent = note.hidden ? "Open our note" : "Close our note";
    });

    document.getElementById("motionButton").addEventListener("click", (event) => {
      const isCalm = document.body.classList.toggle("calm");
      event.currentTarget.setAttribute("aria-pressed", String(isCalm));
      event.currentTarget.textContent = isCalm ? "Enable motion" : "Reduce motion";
      animationEnabled = !isCalm;
    });

    const storyText =
      "Bree & Brian — Our Story\\n\\n" +
      "Our story began on " + dateInput.value + ". " +
      "Every day since has added another moment, memory, and reason to be grateful. " +
      "Here’s to the story we’re still writing together. ♥";

    document.getElementById("copyButton").addEventListener("click", async (event) => {
      const button = event.currentTarget;
      const text = storyText.replace(dateInput.value, dateInput.value);

      try {
        await navigator.clipboard.writeText(text);
        button.textContent = "Copied with love!";
      } catch {
        const area = document.createElement("textarea");
        area.value = text;
        area.style.position = "fixed";
        area.style.opacity = "0";
        document.body.appendChild(area);
        area.select();
        document.execCommand("copy");
        area.remove();
        button.textContent = "Copied with love!";
      }

      setTimeout(() => { button.textContent = "Copy our story"; }, 2200);
    });

    document.getElementById("shareButton").addEventListener("click", async (event) => {
      const button = event.currentTarget;
      const shareData = {
        title: "Bree & Brian — Our Story",
        text: "A little page for a love story that began on October 5.",
        url: window.location.href
      };

      try {
        if (navigator.share) {
          await navigator.share(shareData);
        } else {
          await navigator.clipboard.writeText(window.location.href);
          button.textContent = "Link copied!";
          setTimeout(() => { button.textContent = "Share this page"; }, 2200);
        }
      } catch {
        // A dismissed share sheet is not an error the visitor needs to see.
      }
    });

    // A soft, subtle star field drawn without external libraries.
    const canvas = document.getElementById("stars");
    const context = canvas.getContext("2d");
    let stars = [];
    let animationEnabled = true;

    function resizeCanvas() {
      const ratio = Math.min(window.devicePixelRatio || 1, 2);
      canvas.width = window.innerWidth * ratio;
      canvas.height = window.innerHeight * ratio;
      context.setTransform(ratio, 0, 0, ratio, 0, 0);

      stars = Array.from({ length: Math.min(110, Math.floor(window.innerWidth / 10)) }, () => ({
        x: Math.random() * window.innerWidth,
        y: Math.random() * window.innerHeight,
        radius: Math.random() * 1.3 + 0.25,
        alpha: Math.random() * 0.55 + 0.12,
        speed: Math.random() * 0.18 + 0.025
      }));
    }

    function drawStars() {
      context.clearRect(0, 0, window.innerWidth, window.innerHeight);

      for (const star of stars) {
        context.beginPath();
        context.arc(star.x, star.y, star.radius, 0, Math.PI * 2);
        context.fillStyle = `rgba(246, 220, 229, ${star.alpha})`;
        context.fill();

        if (animationEnabled) {
          star.y -= star.speed;
          if (star.y < -2) {
            star.y = window.innerHeight + 2;
            star.x = Math.random() * window.innerWidth;
          }
        }
      }

      requestAnimationFrame(drawStars);
    }

    window.addEventListener("resize", resizeCanvas);
    resizeCanvas();
    drawStars();
  </script>
</body>
</html>
