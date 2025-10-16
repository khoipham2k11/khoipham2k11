<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Em đồng ý làm người iuu anhh nhaa bé:3</title>
  <style>
    :root{
      --bg1:#fff0f6;
      --bg2:#fff6ec;
      --accent:#ff6b9a;
      --muted:#6b6b6b;
    }
    html,body{height:100%;margin:0;font-family:Inter, "Helvetica Neue", Arial, sans-serif;}
    body{
      display:flex;
      align-items:center;
      justify-content:center;
      background:linear-gradient(160deg,var(--bg1),var(--bg2));
      padding:28px;
      box-sizing:border-box;
    }
    .card{
      width:100%;
      max-width:820px;
      background:linear-gradient(180deg,rgba(255,255,255,0.9),rgba(255,255,255,0.8));
      border-radius:20px;
      box-shadow:0 20px 50px rgba(0,0,0,0.08);
      padding:36px;
      text-align:center;
      position:relative;
      overflow:visible;
    }
    .teddies{
      display:flex;
      gap:10px;
      justify-content:center;
      margin-bottom:14px;
      flex-wrap:wrap;
    }
    .teddy{
      font-size:34px;
      transform:translateY(0);
      transition:transform .35s ease;
    }
    h1{
      margin:10px 0 6px;
      font-size:28px;
      letter-spacing:0.6px;
      color:#333;
    }
    p.lead{
      margin:6px 0 22px;
      color:var(--muted);
      font-size:15px;
    }

    .buttons{
      display:flex;
      gap:18px;
      justify-content:center;
      margin-top:6px;
    }
    button{
      appearance:none;
      border:0;
      padding:12px 20px;
      font-size:16px;
      border-radius:12px;
      cursor:pointer;
      user-select:none;
      display:inline-flex;
      gap:10px;
      align-items:center;
      box-shadow:0 8px 20px rgba(0,0,0,0.06);
      transition:transform .12s ease, box-shadow .12s ease;
    }
    button:active{transform:translateY(2px)}
    .yes{
      background:linear-gradient(90deg,#ff9bb8,#ff6b9a);
      color:white;
    }
    .no{
      background:transparent;
      color:#333;
      border:1px solid rgba(0,0,0,0.06);
    }

    /* modal */
    .modal{
      position:fixed;
      inset:0;
      display:flex;
      align-items:center;
      justify-content:center;
      background:rgba(0,0,0,0.35);
      opacity:0;
      pointer-events:none;
      transition:opacity .18s ease;
    }
    .modal.show{opacity:1;pointer-events:auto;}
    .modal-card{
      background:white;
      padding:26px 28px;
      border-radius:14px;
      max-width:560px;
      text-align:center;
      box-shadow:0 20px 50px rgba(0,0,0,0.18);
    }
    .modal-card h2{margin:6px 0 14px;font-size:22px}
    .emoji-big{font-size:48px;display:block;margin:8px 0 6px}
    .close{
      margin-top:16px;
      padding:10px 14px;
      border-radius:10px;
      border:0;
      background:#f0f0f0;
      cursor:pointer;
    }

    /* footer / small */
    .note{margin-top:18px;color:#777;font-size:13px}
    @media (max-width:480px){
      .card{padding:20px}
      .teddy{font-size:28px}
      h1{font-size:20px}
    }
  </style>
</head>
<body>
  <div class="card" id="card">
    <div class="teddies" aria-hidden="true">
      <div class="teddy">🧸</div>
      <div class="teddy">🧸</div>
      <div class="teddy">🧸</div>
      <div class="teddy">🫶</div>
      <div class="teddy">💫</div>
    </div>

    <h1>Em đồng ý làm người iuu anhh nhaa bé:3</h1>
    <p class="lead">Thoát ra hoặc không chọn thì làm vợ anhh</p>

    <div class="buttons">
      <button class="yes" id="yesBtn">
        <span>🥰</span>
        <span>Có ạ</span>
      </button>

      <button class="no" id="noBtn">
        <span>😅</span>
        <span>Khôngg</span>
      </button>
    </div>

    <div class="note">Nhấn <strong>Có ạ</strong> để nhận lời ngọt ngào (hoặc thử bắt <strong>Khôngg</strong> xem nó có né không 😉)</div>
  </div>

  <!-- Modal -->
  <div class="modal" id="modal" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal-card" role="document">
      <div class="emoji-big">🥰</div>
      <h2>Anh mãi mãi yêu em thật lòng</h2>
      <p>Anh hứa sẽ luôn bên em, chăm sóc và trân trọng em mỗi ngày. 💖</p>
      <button class="close" id="closeModal">Ok, biết rồi!</button>
    </div>
  </div>

  <script>
    (function(){
      const yes = document.getElementById('yesBtn');
      const no = document.getElementById('noBtn');
      const modal = document.getElementById('modal');
      const closeModal = document.getElementById('closeModal');
      const card = document.getElementById('card');

      // Khi nhấn "Có ạ" -> hiện modal
      yes.addEventListener('click', function(){
        modal.classList.add('show');
        modal.setAttribute('aria-hidden', 'false');
        // một chút animation cho các teddy
        document.querySelectorAll('.teddy').forEach((t,i)=>{
          t.style.transform = 'translateY(-6px)';
          setTimeout(()=> t.style.transform = '', 700 + i*60);
        });
      });

      closeModal.addEventListener('click', function(){
        modal.classList.remove('show');
        modal.setAttribute('aria-hidden', 'true');
      });

      // Nút "Khôngg" né khi hover / cố bấm
      function randomPos(el){
        const rect = card.getBoundingClientRect();
        const btnRect = el.getBoundingClientRect();
        const padding = 12;
        const maxX = Math.max(0, rect.width - btnRect.width - padding*2);
        const maxY = Math.max(0, rect.height - btnRect.height - padding*2);
        const x = Math.floor(Math.random() * maxX) + padding;
        const y = Math.floor(Math.random() * maxY) + padding;
        el.style.position = 'absolute';
        el.style.left = x + 'px';
        el.style.top = y + 'px';
      }

      // cứ vài lần nhảy 1 lần khi hover
      let dodgeCount = 0;
      no.addEventListener('mouseenter', function(){
        dodgeCount++;
        if (dodgeCount < 6){
          randomPos(no);
        } else {
          // sau vài lần, nếu user thật sự cố bắt, thì cho phép click nhưng show 1 text playfull
          no.style.position = 'static';
        }
      });

      // phòng trường hợp chạm trên mobile - di chuyển khi touchstart
      no.addEventListener('touchstart', function(e){
        randomPos(no);
      }, {passive:true});

      // Nếu người dùng cố gắng click "Khôngg" (desktop) -> cũng né
      no.addEventListener('click', function(e){
        e.preventDefault();
        randomPos(no);
      });
    })();
  </script>
</body>
</html>
