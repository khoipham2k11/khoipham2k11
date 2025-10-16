const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const bgMusic = document.getElementById("bgMusic");
const heartsContainer = document.getElementById("hearts");

// Khi bấm "Có"
yesBtn.addEventListener("click", () => {
  document.body.innerHTML = `
    <div style="text-align:center; margin-top: 100px;">
      <h1>Anh mãi mãi yêu em thật lòng 🥰</h1>
      <img src="mocha2.gif" width="250" alt="love">
    </div>
  `;
  bgMusic.play();
});

// Khi di chuột hoặc bấm gần nút "Không", nó chạy trốn 😆
function moveButton() {
  const x = Math.random() * (window.innerWidth - noBtn.clientWidth);
  const y = Math.random() * (window.innerHeight - noBtn.clientHeight);
  noBtn.style.position = "absolute";
  noBtn.style.left = `${x}px`;
  noBtn.style.top = `${y}px`;
}

noBtn.addEventListener("mouseover", moveButton);
noBtn.addEventListener("click", moveButton);

// Cho phép nhạc phát khi người dùng tương tác lần đầu
document.body.addEventListener("click", () => {
  bgMusic.play();
});

// Tạo tim bay ngẫu nhiên
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.textContent = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = Math.random() * 20 + 15 + "px";
  heartsContainer.appendChild(heart);

  setTimeout(() => heart.remove(), 5000);
}

setInterval(createHeart, 500);
