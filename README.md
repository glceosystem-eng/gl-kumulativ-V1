<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8" />
  <title>GL CEO Dashboard – Přehled</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      background-color: #f9f7f4;
      color: #111;
      font-family: -apple-system, BlinkMacSystemFont, system-ui, sans-serif;
      -webkit-font-smoothing: antialiased;
    }
    .page {
      max-width: 1100px;
      margin: 0 auto;
      padding: 40px 20px 80px;
    }
    .logo-wrap {
      display: flex;
      justify-content: center;
      margin-bottom: 24px;
    }
    .logo-wrap img {
      max-width: 260px;
      height: auto;
    }
    .headline-block {
      text-align: center;
      margin-bottom: 40px;
    }
    .eyebrow {
      font-size: 11px;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      opacity: 0.55;
      margin-bottom: 6px;
    }
    h1 {
      font-family: "Didot", "Bodoni MT", "Times New Roman", serif;
      font-weight: 400;
      font-size: 28px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 10px;
    }
    .subtitle {
      font-size: 14px;
      opacity: 0.75;
      max-width: 520px;
      margin: 0 auto;
      line-height: 1.6;
    }

    .nav-pills {
      display: flex;
      justify-content: center;
      gap: 12px;
      margin: 30px 0 10px;
      flex-wrap: wrap;
    }
    .nav-pill {
      padding: 10px 26px;
      border-radius: 999px;
      border: 1px solid rgba(0,0,0,0.06);
      background: #fff;
      font-size: 13px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      text-decoration: none;
      color: #444;
      box-shadow: 0 8px 24px rgba(0,0,0,0.04);
      transition: all 0.18s ease;
    }
    .nav-pill:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 30px rgba(0,0,0,0.08);
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
      margin-top: 30px;
    }

    .card {
      background: #ffffff;
      border-radius: 24px;
      padding: 22px 22px 24px;
      box-shadow:
        0 14px 40px rgba(0, 0, 0, 0.06),
        0 1px 0 rgba(255, 255, 255, 0.5);
      border: 1px solid rgba(0, 0, 0, 0.03);
    }
    .card h2 {
      font-size: 15px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      margin-bottom: 10px;
      opacity: 0.8;
    }
    .card p {
      font-size: 13px;
      line-height: 1.6;
      opacity: 0.8;
      margin-bottom: 12px;
    }
    .card a {
      font-size: 13px;
      text-decoration: none;
      color: #b1814b;
      font-weight: 500;
    }
    .card a:hover {
      text-decoration: underline;
    }

    @media (max-width: 768px) {
      .page { padding: 28px 16px 60px; }
      h1 { font-size: 22px; }
    }
  </style>
</head>
<body>
  <!-- LOGIN obrazovka -->
  <div id="login-screen" style="min-height:100vh;display:flex;align-items:center;justify-content:center;background:#f9f7f4;">
    <form id="login-form" style="background:#ffffff;padding:32px 28px;border-radius:24px;box-shadow:0 14px 40px rgba(0,0,0,0.06);max-width:360px;width:100%;text-align:center;font-family:-apple-system,BlinkMacSystemFont,system-ui,sans-serif;">
      <div style="margin-bottom:20px;">
        <img src="gl-logo.png" alt="Great Lengths logo" style="max-width:220px;height:auto;" />
      </div>
      <div style="font-size:11px;letter-spacing:0.25em;text-transform:uppercase;opacity:0.6;margin-bottom:10px;">
        Internal dashboard
      </div>
      <div style="font-size:14px;opacity:0.8;margin-bottom:18px;">
        Zadej heslo pro vstup do GL CEO dashboardu.
      </div>
      <input
        id="password-input"
        type="password"
        placeholder="Heslo"
        autocomplete="current-password"
        style="width:100%;padding:10px 12px;border-radius:999px;border:1px solid rgba(0,0,0,0.12);font-size:14px;margin-bottom:10px;outline:none;"
      />
      <div id="login-error" style="color:#c64545;font-size:12px;min-height:16px;margin-bottom:10px;"></div>
      <button
        type="submit"
        style="width:100%;padding:10px 12px;border-radius:999px;border:none;background:#111;color:#fff;font-size:13px;letter-spacing:0.16em;text-transform:uppercase;cursor:pointer;"
      >
        Přihlásit
      </button>
    </form>
  </div>

  <!-- PŮVODNÍ OBSAH STRÁNKY -->
  <div id="app" style="display:none;">
    <div class="page">
      <div class="logo-wrap">
        <img src="gl-logo.png" alt="Great Lengths logo" />
      </div>

      <section class="headline-block">
        <div class="eyebrow">Internal performance dashboard</div>
        <h1>GL CEO – přehled reportů</h1>
        <p class="subtitle">
          Tři klíčové pohledy na výkon Great Lengths Slovakia:
          kumulativní tržby, salony v riziku a souhrn měsíců.
          Vyber si report, se kterým chceš pracovat.
        </p>
      </section>

      <nav class="nav-pills">
        <a class="nav-pill" href="kumulativ.html">Kumulativ</a>
        <a class="nav-pill" href="urgent.html">Urgent</a>
        <a class="nav-pill" href="mesice.html">Měsíce</a>
      </nav>

      <section class="cards">
        <article class="card">
          <h2>Kumulativ</h2>
          <p>
            Kumulativní tržby po pracovních dnech:
            aktuální měsíc vs. minulý měsíc vs. plánovaný cíl.
          </p>
          <a href="kumulativ.html">Otevřít kumulativní report →</a>
        </article>

        <article class="card">
          <h2>Urgent – salony v riziku</h2>
          <p>
            Přehled salonů podle počtu dní bez objednávky,
            seřazené podle priority kontaktu.
          </p>
          <a href="urgent.html">Otevřít urgent report →</a>
        </article>

        <article class="card">
          <h2>Měsíce</h2>
          <p>
            Porovnání jednotlivých měsíců v roce –
            jak si vedou celkové tržby vs. plán.
          </p>
          <a href="mesice.html">Otevřít měsíční přehled →</a>
        </article>
      </section>
    </div>
  </div>

  <script>
    const GL_PASSWORD = "gl2025";

    function showApp() {
      const login = document.getElementById("login-screen");
      const app = document.getElementById("app");
      if (login && app) {
        login.style.display = "none";
        app.style.display = "block";
      }
    }

    document.addEventListener("DOMContentLoaded", function () {
      const isAuthed = localStorage.getItem("gl-auth") === "ok";
      if (isAuthed) {
        showApp();
      }

      const form = document.getElementById("login-form");
      const input = document.getElementById("password-input");
      const error = document.getElementById("login-error");

      if (!form || !input) return;

      form.addEventListener("submit", function (e) {
        e.preventDefault();
        const value = (input.value || "").trim();

        if (value === GL_PASSWORD) {
          localStorage.setItem("gl-auth", "ok");
          showApp();
        } else {
          error.textContent = "Nesprávné heslo.";
        }
      });
    });
  </script>
</body>
</html>
