<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>신동욱 이력서</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
    }
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f8f9fa;
      display: flex;
      height: 100vh;
      overflow: hidden;
    }
    .menu-toggle {
      display: none;
      position: fixed;
      top: 20px;
      left: 20px;
      z-index: 1100;
      background: teal;
      color: white;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    .sidebar {
      width: 200px;
      background-color: #fff;
      padding: 20px;
      border-right: 1px solid #ddd;
      overflow-y: auto;
      height: 100vh;
      box-sizing: border-box;
      flex-shrink: 0;
      position: sticky;
      top: 0;
      align-self: flex-start;
      transition: left 0.3s ease;
    }
    .sidebar h3 {
      font-size: 16px;
      margin-bottom: 10px;
      color: teal;
    }
    .sidebar ul {
      list-style: none;
      padding: 0;
    }
    .sidebar ul li {
      margin: 10px 0;
    }
    .sidebar ul li a {
      color: #333;
      text-decoration: none;
    }
    .sidebar ul li a.active {
      font-weight: bold;
      color: teal;
    }
    .sidebar ul li a:hover {
      text-decoration: underline;
    }
    .content {
      flex: 1;
      padding: 40px;
      background-color: #fff;
      overflow-y: auto;
      height: 100vh;
      box-sizing: border-box;
    }
    .section {
      margin-bottom: 40px;
    }
    .section h2 {
      border-bottom: 2px solid #000;
      padding-bottom: 5px;
      font-size: 20px;
    }
    .profile {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .highlight {
      font-size: 26px;
      font-weight: bold;
    }
    .subinfo {
      color: #555;
    }
    .photo {
      width: 150px;
      height: 150px;
      border: 2px solid #ccc;
      object-fit: cover;
    }
    a {
      color: teal;
      text-decoration: none;
    }
    .url-box {
      border: 1px solid #ccc;
      padding: 10px;
      background-color: #f0f0f0;
      font-family: monospace;
      word-break: break-all;
    }
    @media (max-width: 768px) {
      .sidebar {
        position: fixed;
        left: -100%;
        top: 0;
        z-index: 1000;
        background: white;
      }
      .sidebar.open {
        left: 0;
      }
      .menu-toggle {
        display: block;
      }
      body {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <div class="menu-toggle" onclick="toggleMenu()">☰ 메뉴</div>

  <div class="sidebar">
    <h3><a href="#basic">기본 정보</a></h3>
    <ul>
      <li><a href="#skills">기술 스택</a></li>
      <li><a href="#education">학력</a></li>
      <li><a href="#project">프로젝트</a></li>
      <li><a href="#certificate">자격증</a></li>
    </ul>
  </div>

  <div class="content">
    <div class="section" id="basic">
      <div class="profile">
        <div>
          <div class="highlight">신동욱</div>
          <div class="subinfo">동양미래대학교 3학년 재학</div>
          <p>이메일: NetField1111@gmail.com </p>
          <p>GitHub: github.com/LAMA-92</p>
        </div>
        <img src="profile.jpg" alt="프로필 사진" class="photo" />
      </div>
    </div>

    <div class="section" id="skills">
      <h2>기술 스택</h2>
      <p><strong>Front End</strong> : HTML , CSS , JS , React</p>
      <p><strong>Back End</strong> : String Boot , Java</p>
      <p><strong>DB</strong> : MySQL</p>
      <p><strong>기타</strong> : Unity 3D</p>
    </div>

    <div class="section" id="education">
      <h2>학력</h2>
      <p><strong>동양미래대학교</strong> 컴퓨터소프트웨어공학 전공 (졸업 예정)</p>
    </div>

    <div class="section" id="project">
      <h2>프로젝트</h2>
      <p><strong>DMU SOUND</strong></p>
      <p class="subinfo">
        허밍 기반 곡 식별 및 정보 제공 웹 애플리케이션
      </p>
      <p><strong>SpotiFedia</strong></p>
      <p class="subinfo">
        음악 평점 공유용 소셜 리뷰 플랫폼
      </p>
      <p><strong>RE2-Project (가제)</strong></p>
      <p class="subinfo">
        Unity 3D 기반 3인칭 게임 개발 프로젝트
      </p>
    </div>

    <div class="section" id="certificate">
      <h2>자격증</h2>
      <p><strong>정보처리산업기사</strong> (예정)</p>
    </div>
  </div>

  <script>
    const sections = document.querySelectorAll('.section');
    const navLinks = document.querySelectorAll('.sidebar ul li a');
    const content = document.querySelector('.content');

    content.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.clientHeight;
        if (content.scrollTop >= sectionTop - 100) {
          current = section.getAttribute('id');
        }
      });

      navLinks.forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('href').includes(current)) {
          link.classList.add('active');
        }
      });
    });

    function toggleMenu() {
      document.querySelector('.sidebar').classList.toggle('open');
    }
  </script>
</body>
</html>
