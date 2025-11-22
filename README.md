# trangiuudauuu[htmlindex..txt](https://github.com/user-attachments/files/23687152/htmlindex.txt)
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Quà cho Trang iu 💗</title>

<style>
    body {
        margin: 0;
        font-family: 'Poppins', sans-serif;
        animation: bgChange 12s infinite alternate;
        overflow-x: hidden;
        text-align: center;
    }

    @keyframes bgChange {
        0% { background: #ffe1f2; }
        50% { background: #ffd0ea; }
        100% { background: #ffc1e5; }
    }

    /* Màn hình nhập mật khẩu */
    #login {
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: rgba(255,170,220,0.7);
        backdrop-filter: blur(10px);
        animation: fadeIn 1.2s;
    }

    @keyframes fadeIn { from {opacity:0;} to {opacity:1;} }

    #login img {
        width: 200px;
        animation: bounce 2s infinite;
        filter: drop-shadow(0 0 10px #ff5eb8);
    }

    @keyframes bounce {
        0%,100% { transform: translateY(0); }
        50% { transform: translateY(-10px); }
    }

    input, button {
        padding: 12px 18px;
        font-size: 18px;
        border-radius: 12px;
        border: none;
        outline: none;
        margin-top: 12px;
    }

    button {
        background: #ff5eb8;
        color: white;
        cursor: pointer;
        box-shadow: 0 0 10px #ff5eb8;
    }

    #content {
        display: none;
        padding: 30px 20px;
        animation: fadeIn 1s ease;
    }

    .box {
        background: white;
        width: 85%;
        margin: auto;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 20px #ffb4da;
    }

    #typing {
        font-size: 20px;
        margin-top: 20px;
        white-space: pre-wrap;
        line-height: 1.7;
    }

    /* Icon rơi */
    .pig {
        position: fixed;
        top: -50px;
        font-size: 45px;
        animation: fall linear infinite;
    }

    @keyframes fall {
        to { transform: translateY(120vh); }
    }

    /* Trái tim theo chuột */
    @keyframes fade {
        from { opacity: 1; transform: scale(1); }
        to { opacity: 0; transform: scale(2); }
    }

    /* Chữ rung */
    h1:hover, h2:hover, h3:hover, #typing:hover {
        animation: shake 0.4s;
    }

    @keyframes shake {
        25% { transform: translate(2px, -2px); }
        50% { transform: translate(-2px, 2px); }
        75% { transform: translate(2px, 2px); }
    }

    /* Pháo hoa */
    .firework {
        position: fixed;
        width: 8px;
        height: 8px;
        background: #ff4da6;
        border-radius: 50%;
        pointer-events: none;
    }
</style>
</head>

<body>

<!-- MÀN HÌNH MẬT KHẨU -->
<div id="login">
    <img src="https://i.pinimg.com/originals/6f/b0/e4/6fb0e4e4e8ddd848f1aadfbd5cb00e28.gif">
    <h2>Nhập mật khẩu để gặp điều bất ngờ 😝💗</h2>
    <input id="pw" type="password" placeholder="Nhập mật khẩu...">
    <button onclick="checkPW()">Mở nè 💗</button>
    <p id="wrong" style="color:red; display:none;">Sai rồi nhaaa 🤧 nhập lại điii</p>
</div>

<!-- NỘI DUNG -->
<div id="content">
    <h1 style="color:#ff1493;">Gửi đến trangiuudauuu 💗💗</h1>

    <div class="box">
        <div id="typing"></div>
        <h3 style="margin-top:20px; color:#ff1493;">
            — qắcdeptrai gửi iu xinn gáiii 💗 —
        </h3>
        <h2 style="margin-top:30px; color:#ff4da6;">
            Chúc ngừi tuiii iuuu bủi trưaaaa vuii vẻeee ặ 😝😝
        </h2>
    </div>

    <audio id="bgm" autoplay loop>
        <source src="https://cdn.pixabay.com/audio/2023/04/20/audio_8a52f30064.mp3">
    </audio>
</div>

<script>
/* Mật khẩu */
function checkPW() {
    if (document.getElementById("pw").value === "quocdeptrai") {
        login.style.display = "none";
        content.style.display = "block";
        typeText();
        rainPigs();
        rainHearts();
    } else wrong.style.display = "block";
}

/* Gõ chữ */
const msg =
"hẹee luuuu tuii là qắccc đẹp troaii dayyy :))\n" +
"tuii lunnn ợ đeyy với tranggiuu cụa tuii nèe 🤭\n" +
"néuu coá chuỵn balaalalalal rìi vói iuu thì đừn coá quen kể choa tui bít nkaa.\n" +
"ngừi chiu dẹp chaii :))\n" +
"lóiii chunn là tuii iuuu trang nhấc ặ 💝";

let i = 0;
function typeText() {
    let timer = setInterval(() => {
        typing.textContent += msg[i];
        i++;
        if (i === msg.length) clearInterval(timer);
    }, 45);
}

/* Icon pig rơi */
function rainPigs() {
    setInterval(() => {
        const p = document.createElement("div");
        p.className = "pig";
        p.textContent = "🐷";
        p.style.left = Math.random()*100 + "vw";
        p.style.animationDuration = 3 + Math.random()*3 + "s";
        document.body.appendChild(p);
        setTimeout(() => p.remove(), 6000);
    }, 500);
}

/* Trái tim theo chuột */
document.addEventListener("mousemove", (e) => {
    const heart = document.createElement("div");
    heart.textContent = "💗";
    heart.style.position = "fixed";
    heart.style.left = e.pageX + "px";
    heart.style.top = e.pageY + "px";
    heart.style.pointerEvents = "none";
    heart.style.fontSize = "20px";
    heart.style.animation = "fade 1s linear";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 1000);
});

/* Pháo hoa khi click */
document.addEventListener("click", (e) => {
    for (let i = 0; i < 20; i++) {
        const dot = document.createElement("div");
        dot.classList.add("firework");
        dot.style.left = e.clientX + "px";
        dot.style.top = e.clientY + "px";
        document.body.appendChild(dot);

        const angle = Math.random() * 2 * Math.PI;
        const radius = Math.random() * 120;
        const x = Math.cos(angle)*radius;
        const y = Math.sin(angle)*radius;

        dot.animate([
            { transform: "translate(0,0)", opacity: 1 },
            { transform: `translate(${x}px,${y}px)`, opacity: 0 }
        ], { duration: 900 });

        setTimeout(() => dot.remove(), 900);
    }
});
</script>

</body>
</html>
