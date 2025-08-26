<template>
  <header class="header">
    <div class="header-container">
      <div class="logo">
        <img src="/logo.png" alt="유진건설 로고" class="logo-image">
        <span>YUJIN CONSTRUCTION</span>
      </div>
      <nav class="nav">
        <ul>
          <li class="nav-item">
            <a href="#home">홈</a>
            <div class="submenu">
              <a href="#main">메인페이지</a>
              <a href="#intro">회사소개</a>
              <a href="#vision">비전</a>
              <a href="#history">연혁</a>
            </div>
          </li>
          <li class="nav-item">
            <a href="#about">회사소개</a>
            <div class="submenu">
              <a href="#company">회사개요</a>
              <a href="#ceo">CEO인사</a>
              <a href="#organization">조직도</a>
              <a href="#location">오시는길</a>
            </div>
          </li>
          <li class="nav-item">
            <a href="#projects">사업영역</a>
            <div class="submenu">
              <a href="#architecture">건축공사</a>
              <a href="#civil">토목공사</a>
              <a href="#industrial">산업시설</a>
              <a href="#housing">주택개발</a>
            </div>
          </li>
          <li class="nav-item">
            <a href="#news">뉴스</a>
            <div class="submenu">
              <a href="#notice">공지사항</a>
              <a href="#press">보도자료</a>
              <a href="#awards">수상실적</a>
              <a href="#gallery">갤러리</a>
            </div>
          </li>
          <li class="nav-item">
            <a href="#contact">고객지원</a>
            <div class="submenu">
              <a href="#inquiry">문의하기</a>
              <a href="#estimate">견적요청</a>
              <a href="#recruit">채용정보</a>
              <a href="#download">자료실</a>
            </div>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup>
// Header 컴포넌트 로직
</script>

<style scoped>
.header {
  background: #23c74c;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
}

.header-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
}

.logo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.logo-image {
  height: 50px;
  width: auto;
  margin-bottom: 5px;
}

.logo span {
  color: #1505f1;
  font-size: 12px;
  font-weight: 500;
}

.nav ul {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-item {
  margin-left: 100px;
  position: relative;
  font-size: 20px;
}

.nav a {
  text-decoration: none;
  color: #ffffff;
  font-weight: 500;
  transition: color 0.3s;
  padding: 20px 0;
  display: block;
}

.nav a:hover {
  color: #3498db;
}

/* 서브메뉴 스타일 */
.submenu {
  position: absolute;
  top: 100%;
  left: 0;
  background: white;
  min-width: 180px;
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
  border-radius: 8px;
  opacity: 0;
  visibility: hidden;
  transform: translateY(-10px);
  transition: all 0.3s ease;
  padding: 15px 0;
}

.nav-item:hover .submenu {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
}

.submenu a {
  padding: 12px 20px;
  color: #2600ff;
  font-size: 14px;
  border-bottom: 1px solid #f0f0f0;
  transition: all 0.3s;
}

.submenu a:last-child {
  border-bottom: none;
}

.submenu a:hover {
  background: #f8f9fa;
  color: #3498db;
  padding-left: 25px;
}

/* 반응형 */
@media (max-width: 768px) {
  .nav {
    display: none;
  }
}
</style>
