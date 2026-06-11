<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WOON | Portfolio</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Montserrat:wght@600;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">

<style>
:root{
    --bg:#0f172a;
    --surface:#1e293b;
    --surface-2:#273549;
    --primary:#14b8a6;
    --primary-light:#38bdf8;
    --text:#e2e8f0;
    --muted:#94a3b8;
    --border:rgba(255,255,255,.08);
    --glass:rgba(255,255,255,.05);
    --shadow:0 20px 40px rgba(0,0,0,.35);
    --radius:24px;
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter',sans-serif;
    overflow-x:hidden;
}

body::before{
    content:"";
    position:fixed;
    inset:0;
    background:
    radial-gradient(circle at 20% 20%, rgba(20,184,166,.15), transparent 30%),
    radial-gradient(circle at 80% 10%, rgba(56,189,248,.12), transparent 30%),
    radial-gradient(circle at 50% 80%, rgba(20,184,166,.10), transparent 30%);
    pointer-events:none;
    z-index:-1;
}

.container{
    width:min(1200px,92%);
    margin:auto;
}

header{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    z-index:1000;
    backdrop-filter:blur(18px);
    background:rgba(15,23,42,.75);
    border-bottom:1px solid var(--border);
}

.navbar{
    height:75px;
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.logo{
    font-family:'Montserrat',sans-serif;
    font-size:1.4rem;
    font-weight:800;
    letter-spacing:2px;
}

.logo span{
    color:var(--primary);
}

.nav-links{
    display:flex;
    gap:2rem;
    list-style:none;
}

.nav-links a{
    text-decoration:none;
    color:var(--text);
    transition:.3s;
    font-weight:500;
}

.nav-links a:hover{
    color:var(--primary);
}

.menu-btn{
    display:none;
    width:48px;
    height:48px;
    border:none;
    background:transparent;
    color:var(--text);
    font-size:1.4rem;
    cursor:pointer;
}

.hero{
    min-height:100vh;
    display:flex;
    align-items:center;
    position:relative;
    overflow:hidden;
}

.hero::before{
    content:"";
    position:absolute;
    inset:0;
    background:
    linear-gradient(135deg, rgba(20,184,166,.15), transparent),
    repeating-linear-gradient(
        45deg,
        rgba(255,255,255,.02) 0,
        rgba(255,255,255,.02) 1px,
        transparent 1px,
        transparent 40px
    );
}

.hero-content{
    position:relative;
    z-index:2;
}

.hero h1{
    font-family:'Montserrat',sans-serif;
    font-size:clamp(3rem,7vw,6rem);
    line-height:1;
    margin-bottom:1rem;
}

.hero h1 span{
    color:var(--primary);
}

.hero p{
    max-width:650px;
    color:var(--muted);
    line-height:1.8;
    font-size:1.05rem;
}

.hero-buttons{
    margin-top:2rem;
    display:flex;
    flex-wrap:wrap;
    gap:1rem;
}

.btn{
    min-height:48px;
    padding:14px 24px;
    border-radius:14px;
    border:none;
    cursor:pointer;
    text-decoration:none;
    display:inline-flex;
    align-items:center;
    justify-content:center;
    gap:.6rem;
    transition:.3s;
    font-weight:600;
}

.btn-primary{
    background:var(--primary);
    color:white;
}

.btn-primary:hover{
    transform:translateY(-3px);
    box-shadow:0 15px 30px rgba(20,184,166,.25);
}

.btn-outline{
    border:1px solid rgba(255,255,255,.15);
    background:rgba(255,255,255,.03);
    color:var(--text);
}

.btn-outline:hover{
    background:rgba(255,255,255,.08);
}

.section{
    padding:100px 0;
}

.section-title{
    text-align:center;
    margin-bottom:4rem;
}

.section-title h2{
    font-family:'Montserrat',sans-serif;
    font-size:2.3rem;
    margin-bottom:1rem;
}

.section-title p{
    color:var(--muted);
}

.grid{
    display:grid;
    gap:1.5rem;
}

.about-grid{
    grid-template-columns:1fr;
}

.card{
    background:rgba(30,41,59,.75);
    backdrop-filter:blur(16px);
    border:1px solid var(--border);
    border-radius:var(--radius);
    padding:2rem;
    transition:.35s;
    box-shadow:var(--shadow);
}

.card:hover{
    transform:translateY(-8px);
    border-color:rgba(20,184,166,.35);
}

.profile-card{
    text-align:center;
}

.avatar{
    width:120px;
    height:120px;
    border-radius:50%;
    margin:auto;
    background:linear-gradient(135deg,var(--primary),var(--primary-light));
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:3rem;
    font-weight:800;
    margin-bottom:1.2rem;
}

.info-list{
    display:grid;
    gap:1rem;
}

.info-item{
    display:flex;
    justify-content:space-between;
    gap:1rem;
    padding:1rem;
    background:rgba(255,255,255,.03);
    border-radius:14px;
}

.label{
    color:var(--muted);
}

.value{
    font-weight:600;
}

.skills{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
    gap:1.2rem;
}

.skill{
    text-align:center;
}

.skill i{
    font-size:2rem;
    color:var(--primary);
    margin-bottom:1rem;
}

.contact-card{
    text-align:center;
}

.contact-email{
    display:inline-flex;
    align-items:center;
    gap:.8rem;
    margin-top:1rem;
    color:var(--primary-light);
    text-decoration:none;
    font-weight:600;
    word-break:break-all;
}

.fade{
    opacity:0;
    transform:translateY(40px);
    transition:all .9s ease;
}

.fade.show{
    opacity:1;
    transform:translateY(0);
}

footer{
    padding:40px 0;
    border-top:1px solid var(--border);
    text-align:center;
    color:var(--muted);
}

@media (min-width:768px){
    .about-grid{
        grid-template-columns:380px 1fr;
    }
}

@media (max-width:767px){

    .nav-links{
        position:absolute;
        top:75px;
        right:0;
        width:100%;
        flex-direction:column;
        background:#111c33;
        padding:1rem;
        border-top:1px solid var(--border);
        display:none;
    }

    .nav-links.active{
        display:flex;
    }

    .menu-btn{
        display:block;
    }

    .hero{
        text-align:center;
    }

    .hero-buttons{
        justify-content:center;
    }

    .info-item{
        flex-direction:column;
    }
}
</style>
</head>
<body>

<header>
    <div class="container navbar">
        <div class="logo">W<span>OON</span></div>

        <ul class="nav-links" id="navMenu">
            <li><a href="#home">홈</a></li>
            <li><a href="#about">소개</a></li>
            <li><a href="#interests">관심사</a></li>
            <li><a href="#contact">연락처</a></li>
        </ul>

        <button class="menu-btn" id="menuBtn" aria-label="메뉴 열기">
            <i class="fas fa-bars"></i>
        </button>
    </div>
</header>

<main>

<section class="hero" id="home">
    <div class="container hero-content fade">
        <h1> <span>WOON</span> </h1>

        <p>
            감성과 창의성을 중요하게 생각하는 사람입니다.
            Drawing을 즐기며, 섬세한 관찰력과 자유로운 표현을 통해
            새로운 아이디어를 만들어가는 것을 좋아합니다.
            디저트와 동물을 사랑하며, 일상 속 작은 즐거움에서 영감을 얻습니다.
        </p>

        <div class="hero-buttons">
            <a href="#about" class="btn btn-primary">
                <i class="fas fa-user"></i>
                자기소개 보기
            </a>

            <a href="#contact" class="btn btn-outline">
                <i class="fas fa-envelope"></i>
                연락하기
            </a>
        </div>
    </div>
</section>

<section class="section" id="about">
    <div class="container">

        <div class="section-title fade">
            <h2>프로필</h2>
            <p>기본 정보와 성향을 소개합니다.</p>
        </div>

        <div class="grid about-grid">

            <div class="card profile-card fade">
                <img
    src="IMG_0160.png"
    alt="WOON 프로필 사진"
    class="profile-image"

    .profile-image{
    width:140px;
    height:140px;
    border-radius:50%;
    object-fit:cover;
    display:block;
    margin:0 auto 1.5rem;
    border:4px solid rgba(20,184,166,.6);
    box-shadow:
        0 0 0 8px rgba(20,184,166,.12),
        0 20px 40px rgba(0,0,0,.35);
    transition:.4s;
}

.profile-image:hover{
    transform:scale(1.05);
}
/>

.profile-image:hover{
    transform:scale(1.05);
}
                <h3>WOON</h3>
                <p style="color:var(--muted); margin-top:10px;">
                    Creative • ISFP • Drawing Lover
                </p>
            </div>

            <div class="card fade">
                <div class="info-list">

                    <div class="info-item">
                        <span class="label">이름</span>
                        <span class="value">WOON</span>
                    </div>

                    <div class="info-item">
                        <span class="label">취미</span>
                        <span class="value">Drawing</span>
                    </div>

                    <div class="info-item">
                        <span class="label">MBTI</span>
                        <span class="value">ISFP</span>
                    </div>

                    <div class="info-item">
                        <span class="label">혈액형</span>
                        <span class="value">RH+A</span>
                    </div>

                    <div class="info-item">
                        <span class="label">좋아하는 것</span>
                        <span class="value">디저트, 동물</span>
                    </div>

                </div>
            </div>

        </div>

    </div>
</section>

<section class="section" id="interests">
    <div class="container">

        <div class="section-title fade">
            <h2>관심 분야</h2>
            <p>제가 좋아하고 즐기는 것들입니다.</p>
        </div>

        <div class="skills">

            <div class="card skill fade">
                <i class="fas fa-pencil-alt"></i>
                <h3>Drawing</h3>
                <p style="color:var(--muted);margin-top:10px;">
                    창의적인 표현과 시각적 스토리텔링을 즐깁니다.
                </p>
            </div>

            <div class="card skill fade">
                <i class="fas fa-cake-candles"></i>
                <h3>디저트</h3>
                <p style="color:var(--muted);margin-top:10px;">
                    새로운 맛과 감성을 경험하는 것을 좋아합니다.
                </p>
            </div>

            <div class="card skill fade">
                <i class="fas fa-paw"></i>
                <h3>동물</h3>
                <p style="color:var(--muted);margin-top:10px;">
                    동물과 함께하는 따뜻한 순간을 소중하게 생각합니다.
                </p>
            </div>

            <div class="card skill fade">
                <i class="fas fa-heart"></i>
                <h3>감성 & 창의성</h3>
                <p style="color:var(--muted);margin-top:10px;">
                    자유로운 표현과 개성 있는 아이디어를 추구합니다.
                </p>
            </div>

        </div>

    </div>
</section>

<section class="section" id="contact">
    <div class="container">

        <div class="section-title fade">
            <h2>연락처</h2>
            <p>언제든지 편하게 연락해 주세요.</p>
        </div>

        <div class="card contact-card fade">

            <i class="fas fa-envelope" style="font-size:2.2rem;color:var(--primary);"></i>

            <h3 style="margin-top:1rem;">이메일</h3>

            <a class="contact-email" href="mailto:sungju.woon@gmail.com" aria-label="이메일 보내기">
                <i class="fas fa-paper-plane"></i>
                sungju.woon@gmail.com
            </a>

        </div>

    </div>
</section>

</main>

<footer>
    <div class="container">
        © 2026 WOON Portfolio. All Rights Reserved.
    </div>
</footer>

<script>
const menuBtn = document.getElementById('menuBtn');
const navMenu = document.getElementById('navMenu');

menuBtn.addEventListener('click', () => {
    navMenu.classList.toggle('active');
});

document.querySelectorAll('.nav-links a').forEach(link=>{
    link.addEventListener('click',()=>{
        navMenu.classList.remove('active');
    });
});

const observer = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
        if(entry.isIntersecting){
            entry.target.classList.add('show');
        }
    });
},{
    threshold:0.15
});

document.querySelectorAll('.fade').forEach(el=>{
    observer.observe(el);
});
</script>

</body>
</html>
