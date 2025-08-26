<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-content">
        <div class="footer-section">
          <h3>유진건설</h3>
          <p>건설의 미래를 만들어가는<br>신뢰할 수 있는 파트너</p>
        </div>
        
        <div class="footer-section">
          <h4>사업 영역</h4>
          <ul>
            <li><a href="#projects">건축 공사</a></li>
            <li><a href="#projects">토목 공사</a></li>
            <li><a href="#projects">산업시설</a></li>
            <li><a href="#projects">주택 개발</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>고객지원</h4>
          <ul>
            <li><a href="#contact">문의하기</a></li>
            <li><a href="#contact">견적 요청</a></li>
            <li><a href="#contact">채용 정보</a></li>
            <li><a href="#contact">뉴스</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>연락처</h4>
          <div class="contact-info">
            <p>📞 02-1234-5678</p>
            <p>📧 info@yujin.co.kr</p>
            <p>📍 서울특별시 강남구 테헤란로 123</p>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <div class="footer-bottom-content">
          <p>&copy; 2024 유진건설. All rights reserved.</p>
          <div class="social-links">
            <a href="#" class="social-link">📘</a>
            <a href="#" class="social-link">📷</a>
            <a href="#" class="social-link">🐦</a>
            <a href="#" class="social-link">📺</a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
// Footer 컴포넌트 로직
</script>

<style scoped>
.footer {
  background: #2c3e50;
  color: white;
  padding: 60px 0 20px;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-bottom: 40px;
}

.footer-section h3 {
  font-size: 24px;
  margin-bottom: 15px;
  color: #3498db;
}

.footer-section h4 {
  font-size: 18px;
  margin-bottom: 15px;
  color: #ecf0f1;
}

.footer-section p {
  color: #bdc3c7;
  line-height: 1.6;
  margin-bottom: 10px;
}

.footer-section ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-section li {
  margin-bottom: 8px;
}

.footer-section a {
  color: #bdc3c7;
  text-decoration: none;
  transition: color 0.3s;
}

.footer-section a:hover {
  color: #3498db;
}

.contact-info p {
  margin-bottom: 8px;
  color: #bdc3c7;
}

.footer-bottom {
  border-top: 1px solid #34495e;
  padding-top: 20px;
}

.footer-bottom-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.footer-bottom p {
  color: #95a5a6;
  margin: 0;
}

.social-links {
  display: flex;
  gap: 15px;
}

.social-link {
  color: #bdc3c7;
  font-size: 20px;
  text-decoration: none;
  transition: color 0.3s;
}

.social-link:hover {
  color: #3498db;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .footer-bottom-content {
    flex-direction: column;
    gap: 20px;
    text-align: center;
  }
}
</style>
