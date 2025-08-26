<template>
  <section class="slide-section">
    <!-- 슬라이드 배경 -->
    <div class="slide-background">
      <div 
        v-for="(slide, index) in slides" 
        :key="index"
        :class="['slide-bg', { active: currentSlide === index }]"
        :style="{ backgroundImage: `url(${slide.image})` }"
      ></div>
    </div>
    
    <div class="slide-overlay"></div>
    
    <div class="slide-container">
      <div class="slide-content">
        <h2>{{ slides[currentSlide].title }}</h2>
        <p>{{ slides[currentSlide].description }}</p>
        <button class="cta-button" @click="showPopup = true">자세히 보기</button>
      </div>
      
      <!-- 슬라이드 인디케이터 -->
      <div class="slide-indicators">
        <button 
          v-for="(slide, index) in slides" 
          :key="index"
          :class="['indicator', { active: currentSlide === index }]"
          @click="goToSlide(index)"
        ></button>
      </div>
    </div>

    <!-- 자세히 보기 팝업 -->
    <div v-if="showPopup" class="popup-overlay" @click="showPopup = false">
      <div class="popup-content" @click.stop>
        <div class="popup-header">
          <h3>{{ slides[currentSlide].popupTitle }}</h3>
          <button class="popup-close" @click="showPopup = false">×</button>
        </div>
        <div class="popup-body">
          <div class="popup-image">
            <img :src="slides[currentSlide].image" :alt="slides[currentSlide].popupTitle">
          </div>
          <div class="popup-text">
            <h4>{{ slides[currentSlide].popupSubtitle }}</h4>
            <p>{{ slides[currentSlide].popupDescription }}</p>
            <ul class="popup-features">
              <li v-for="feature in slides[currentSlide].features" :key="feature">
                {{ feature }}
              </li>
            </ul>
          </div>
        </div>
        <div class="popup-footer">
          <button class="popup-btn primary" @click="showPopup = false">확인</button>
          <button class="popup-btn secondary" @click="showPopup = false">닫기</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
const showPopup = ref(false)
let slideInterval = null

const slides = ref([
  {
    image: 'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    title: '건설의 미래를',
    description: '혁신적인 건설 기술과 지속가능한 발전을 통해 더 나은 내일을 건설합니다',
    popupTitle: '건설의 미래',
    popupSubtitle: '혁신적인 건설 기술',
    popupDescription: '유진건설은 최신 건설 기술과 친환경 건축 자재를 활용하여 지속가능한 건설을 실현합니다.',
    features: [
      '친환경 건축 자재 사용',
      '최신 BIM 기술 적용',
      '에너지 효율성 극대화',
      '스마트 건설 시스템'
    ]
  },
  {
    image: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    title: '전문성과 신뢰로',
    description: '30년간 쌓아온 건설 경험과 기술력으로 고객의 꿈을 현실로 만듭니다',
    popupTitle: '전문성과 신뢰',
    popupSubtitle: '30년 건설 경험',
    popupDescription: '30년간 축적된 건설 노하우와 전문 기술력으로 고객의 요구사항을 정확히 파악하고 최고 품질의 건설 서비스를 제공합니다.',
    features: [
      '30년 건설 경험',
      '전문 기술진 보유',
      '품질 관리 시스템',
      '고객 만족도 최우선'
    ]
  },
  {
    image: 'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    title: '지속가능한 건설은',
    description: '환경을 생각하는 친환경 건설 기술로 미래 세대를 위한 건설을 이어갑니다',
    popupTitle: '지속가능한 건설',
    popupSubtitle: '친환경 건설 기술',
    popupDescription: '환경 보호와 자원 절약을 고려한 친환경 건설 기술을 개발하고 적용하여 미래 세대를 위한 지속가능한 건설을 실현합니다.',
    features: [
      '친환경 건축 인증',
      '재생 에너지 시스템',
      '자원 순환 건설',
      '탄소 중립 목표'
    ]
  }
])

const goToSlide = (index) => {
  currentSlide.value = index
}

const startSlideShow = () => {
  slideInterval = setInterval(() => {
    currentSlide.value = (currentSlide.value + 1) % slides.value.length
  }, 5000)
}

onMounted(() => {
  startSlideShow()
})

onUnmounted(() => {
  if (slideInterval) {
    clearInterval(slideInterval)
  }
})
</script>

<style scoped>
.slide-section {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 80px;
  overflow: hidden;
}

.slide-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.slide-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  opacity: 0;
  transition: opacity 1s ease-in-out;
}

.slide-bg.active {
  opacity: 1;
}

.slide-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4);
  z-index: 1;
}

.slide-container {
  position: relative;
  z-index: 2;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.slide-content h2 {
  color: white;
  font-size: 48px;
  font-weight: bold;
  margin-bottom: 20px;
  line-height: 1.2;
}

.slide-content p {
  color: rgba(255, 255, 255, 0.9);
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 30px;
}

.cta-button {
  background: #e74c3c;
  color: white;
  border: none;
  padding: 15px 30px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s;
}

.cta-button:hover {
  background: #c0392b;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(231, 76, 60, 0.4);
    z-index: 20;
}

.slide-indicators {
  position: absolute;
  bottom: 50px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 15px;
  z-index: 3;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: 2px solid white;
  background: transparent;
  cursor: pointer;
  transition: all 0.3s;
  position: relative;
  top:250px;
}

.indicator.active {
  background: white;
}

.indicator:hover {
  background: rgba(255, 255, 255, 0.7);
}

/* 팝업 스타일 */
.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10000;
  animation: fadeIn 0.3s ease;
}

.popup-content {
  background: white;
  border-radius: 15px;
  max-width: 800px;
  width: 90%;
  max-height: 90vh;
  overflow-y: auto;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  animation: slideUp 0.3s ease;
}

.popup-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px 30px;
  border-bottom: 1px solid #eee;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-radius: 15px 15px 0 0;
}

.popup-header h3 {
  margin: 0;
  font-size: 24px;
  font-weight: bold;
}

.popup-close {
  background: none;
  border: none;
  color: white;
  font-size: 28px;
  cursor: pointer;
  padding: 0;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: background 0.3s;
}

.popup-close:hover {
  background: rgba(255, 255, 255, 0.2);
}

.popup-body {
  padding: 30px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
}

.popup-image img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.popup-text h4 {
  color: #2c3e50;
  margin: 0 0 15px 0;
  font-size: 20px;
}

.popup-text p {
  color: #7f8c8d;
  line-height: 1.6;
  margin-bottom: 20px;
}

.popup-features {
  list-style: none;
  padding: 0;
  margin: 0;
}

.popup-features li {
  padding: 8px 0;
  color: #2c3e50;
  position: relative;
  padding-left: 25px;
}

.popup-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #27ae60;
  font-weight: bold;
}

.popup-footer {
  padding: 20px 30px;
  border-top: 1px solid #eee;
  display: flex;
  gap: 15px;
  justify-content: flex-end;
}

.popup-btn {
  padding: 12px 25px;
  border: none;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s;
}

.popup-btn.primary {
  background: #3498db;
  color: white;
}

.popup-btn.primary:hover {
  background: #2980b9;
  transform: translateY(-2px);
}

.popup-btn.secondary {
  background: #95a5a6;
  color: white;
}

.popup-btn.secondary:hover {
  background: #7f8c8d;
  transform: translateY(-2px);
}

/* 애니메이션 */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 반응형 */
@media (max-width: 768px) {
  .slide-container {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .slide-content h2 {
    font-size: 36px;
  }
  
  .slide-indicators {
    bottom: 30px;
  }
  
  .popup-body {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .popup-content {
    width: 95%;
    margin: 20px;
  }
  
  .popup-header,
  .popup-body,
  .popup-footer {
    padding: 20px;
  }
}
</style>
