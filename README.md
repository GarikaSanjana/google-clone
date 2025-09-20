# google-clone
My clone repository
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Google — Clone (HTML & CSS)</title>
  <style>
    /* ---------- Reset & base ---------- */
    ,::before,*::after{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Roboto", "Helvetica Neue", Arial, sans-serif;
      color:#202124;
      background: #fff;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      display:flex;
      flex-direction:column;
      min-height:100vh;
    }

    /* ---------- Center area ---------- */
    .main{
      flex:1 0 auto;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:40px 20px;
    }

    .content{
      width:100%;
      max-width:740px;
      text-align:center;
    }

    /* ---------- Logo (text-based, Google colors) ---------- */
    .logo{
      font-weight:700;
      font-size:92px;
      line-height:1;
      margin:18px 0 36px;
      letter-spacing: -2px;
      user-select:none;
    }
    .logo .g{ color:#4285F4; }
    .logo .o1{ color:#DB4437; }
    .logo .o2{ color:#F4B400; }
    .logo .g2{ color:#4285F4; }
    .logo .l{ color:#0F9D58; }
    .logo .e{ color:#DB4437; }

    /* Reduce logo size on small screens */
    @media (max-width:420px){
      .logo{ font-size:56px; margin-bottom:20px; }
    }

    /* ---------- Search box ---------- */
    .search-wrap{
      display:flex;
      align-items:center;
      background:#fff;
      border:1px solid #dfe1e5;
      box-shadow:0 1px 6px rgba(32,33,36,.28);
      border-radius:24px;
      padding:10px 14px;
      max-height:44px;
      transition:box-shadow .15s, border-color .15s;
      margin: 0 auto;
    }
    .search-wrap:focus-within{
      border-color: rgba(66,133,244,.6);
      box-shadow:0 4px 12px rgba(66,133,244,.18);
    }

    .search-icon{
      width:20px;
      height:20px;
      margin-right:12px;
      opacity:.6;
      flex-shrink:0;
    }

    .search-input{
      border:0;
      outline:0;
      font-size:16px;
      flex:1 1 auto;
      min-width:0;
      padding:6px 0;
    }

    .right-icons{
      display:flex;
      gap:8px;
      align-items:center;
      margin-left:8px;
      flex-shrink:0;
    }
    .circle-btn{
      width:36px;
      height:36px;
      border-radius:50%;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      background:transparent;
      border:none;
      cursor:pointer;
      opacity:.65;
      transition:opacity .12s, background .12s;
    }
    .circle-btn:focus{ outline:2px solid rgba(66,133,244,.25); outline-offset:2px; opacity:1; }
    .circle-btn:hover{ opacity:1; background: rgba(60,64,67,.06); }

    /* ---------- Buttons ---------- */
    .buttons{
      margin-top:20px;
      display:flex;
      gap:10px;
      justify-content:center;
      flex-wrap:wrap;
    }
    .btn{
      background:#f8f9fa;
      border:1px solid #f8f9fa;
      padding:10px 18px;
      border-radius:4px;
      font-size:14px;
      cursor:pointer;
      color:#3c4043;
      transition:box-shadow .12s, background .12s;
    }
    .btn:hover{ box-shadow: 0 1px 1px rgba(0,0,0,.05); background:#f1f3f4; }
    .btn:active{ transform: translateY(1px); }

    /* ---------- Footer ---------- */
    footer{
      background:transparent;
      padding:14px 24px;
      border-top:1px solid rgba(0,0,0,.05);
      font-size:14px;
      color:#70757a;
    }
    .footer-inner{
      max-width:980px;
      margin:0 auto;
      display:flex;
      justify-content:space-between;
      gap:12px;
      flex-wrap:wrap;
      align-items:center;
    }
    .left-links a, .right-links a{
      color:inherit;
      text-decoration:none;
      margin-right:16px;
    }
    .left-links a:hover, .right-links a:hover{ text-decoration:underline; }

    /* small screens adjust */
    @media (max-width:560px){
      .search-wrap{ padding-left:10px; padding-right:10px; }
      .buttons{ gap:8px; margin-top:14px; }
      .logo{ margin-bottom:14px; }
    }
  </style>
</head>
<body>
  <main class="main" role="main">
    <div class="content" aria-labelledby="homepage-title">
      <h1 id="homepage-title" class="logo" aria-hidden="true">
        <span class="g">G</span><span class="o1">o</span><span class="o2">o</span><span class="g2">g</span><span class="l">l</span><span class="e">e</span>
      </h1>

      <form class="search-wrap" role="search" action="https://www.google.com/search" method="GET" onsubmit="">
        <!-- left magnifier -->
        <svg class="search-icon" viewBox="0 0 24 24" aria-hidden="true">
          <path fill="currentColor" d="M15.5 14h-.79l-.28-.27A6.471 6.471 0 0 0 16 9.5 6.5 6.5 0 1 0 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zM9.5 14C7 14 5 12 5 9.5S7 5 9.5 5 14 7 14 9.5 12 14 9.5 14z"/>
        </svg>

        <input
          class="search-input"
          name="q"
          type="search"
          placeholder="Search Google or type a URL"
          aria-label="Search"
          autocomplete="off"
          spellcheck="false"
        />

        <div class="right-icons" aria-hidden="true">
          <!-- Voice mic icon -->
          <button type="button" class="circle-btn" title="Search by voice" aria-label="Search by voice" tabindex="-1">
            <svg width="18" height="18" viewBox="0 0 24 24"><path fill="currentColor" d="M12 15a3 3 0 0 0 3-3V6a3 3 0 0 0-6 0v6a3 3 0 0 0 3 3zm5-3a5 5 0 0 1-10 0H5a7 7 0 0 0 14 0h-2zM11 19h2v3h-2v-3z"/></svg>
          </button>

          <!-- Apps/grid icon -->
          <button type="button" class="circle-btn" title="Apps" aria-label="Apps" tabindex="-1">
            <svg width="18" height="18" viewBox="0 0 24 24"><path fill="currentColor" d="M4 4h4v4H4V4zm6 0h4v4h-4V4zm6 0h4v4h-4V4zM4 10h4v4H4v-4zm6 0h4v4h-4v-4zm6 0h4v4h-4v-4zM4 16h4v4H4v-4zm6 0h4v4h-4v-4zm6 0h4v4h-4v-4z"/></svg>
          </button>
        </div>
      </form>

      <div class="buttons" role="group" aria-label="Search buttons">
        <!-- The form above points to Google search. The buttons here are visual; we use a simple JS-free behavior:
             - the first button submits the parent form (search).
             - the second is non-functional "I'm Feeling Lucky". If you want it to navigate to first result, JS is required. -->
        <button class="btn" onclick="this.closest('form').submit()">Google Search</button>
        <button class="btn" onclick="window.location='https://www.google.com/doodles'">I'm Feeling Lucky</button>
      </div>
    </div>
  </main>

  <footer>
    <div class="footer-inner" role="contentinfo">
      <div class="left-links">
        <span>India</span>
      </div>
      <div class="right-links" aria-hidden="false">
        <a href="#">Advertising</a>
        <a href="#">Business</a>
        <a href="#">About</a>
        <a href="#">Privacy</a>
        <a href="#">Terms</a>
        <a href="#">Settings</a>
      </div>
    </div>
  </footer>
</body>
</html>
