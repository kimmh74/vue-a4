<template>
  <section class="contents-section">
    <div class="contents-container">
      <!-- 회사 소개 섹션 -->
      <div class="content-block" id="about">
        <h2>회사 소개</h2>
        <div class="content-grid">
          <div class="content-item" @click="showPopup('philosophy')">
            <div class="icon">🏢</div>
            <h3>기업 철학</h3>
            <p>고객 만족과 사회 발전을 위한 건설 서비스 제공</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="content-item" @click="showPopup('vision')">
            <div class="icon">🎯</div>
            <h3>비전</h3>
            <p>건설 산업의 선도자로서 지속가능한 미래 건설</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="content-item" @click="showPopup('innovation')">
            <div class="icon">💡</div>
            <h3>혁신</h3>
            <p>최신 기술과 창의적 아이디어로 건설의 새로운 패러다임 제시</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
        </div>
      </div>

      <!-- 건설 현장 이미지 갤러리 -->
      <div class="content-block">
        <h2>건설 현장</h2>
        <div class="construction-gallery">
          <div class="gallery-item" @click="showPopup('construction1')">
            <img src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="현대적인 건축물">
            <div class="gallery-overlay">
              <h3>현대적인 건축물</h3>
              <p>최신 건설 기술로 완성된 현대적 건축물</p>
            </div>
          </div>
          <div class="gallery-item" @click="showPopup('construction2')">
            <img src="https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="전문적인 시공">
            <div class="gallery-overlay">
              <h3>전문적인 시공</h3>
              <p>숙련된 전문가들의 정밀한 시공 과정</p>
            </div>
          </div>
          <div class="gallery-item" @click="showPopup('construction3')">
            <img src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="안전한 작업환경">
            <div class="gallery-overlay">
              <h3>안전한 작업환경</h3>
              <p>안전을 최우선으로 하는 건설 현장</p>
            </div>
          </div>
        </div>
      </div>

      <!-- 사업 영역 섹션 -->
      <div class="content-block" id="projects">
        <h2>사업 영역</h2>
        <div class="projects-grid">
          <div class="project-card" @click="showPopup('architecture')">
            <div class="project-image">🏗️</div>
            <h3>건축 공사</h3>
            <p>상업시설, 주거시설, 공공시설 등 다양한 건축물 시공</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="project-card" @click="showPopup('civil')">
            <div class="project-image">🌉</div>
            <h3>토목 공사</h3>
            <p>도로, 교량, 터널 등 사회기반시설 건설</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="project-card" @click="showPopup('industrial')">
            <div class="project-image">🏭</div>
            <h3>산업시설</h3>
            <p>공장, 발전소, 정유시설 등 산업시설 건설</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="project-card" @click="showPopup('housing')">
            <div class="project-image">🏠</div>
            <h3>주택 개발</h3>
            <p>아파트, 단독주택, 상가 등 주거시설 개발</p>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
        </div>
      </div>

      <!-- 주요 실적 섹션 -->
      <div class="content-block">
        <h2>주요 실적</h2>
        <div class="achievements">
          <div class="achievement-item" @click="showPopup('achievement1')">
            <div class="number">500+</div>
            <div class="label">완공 프로젝트</div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="achievement-item" @click="showPopup('achievement2')">
            <div class="number">30년+</div>
            <div class="label">건설 경험</div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="achievement-item" @click="showPopup('achievement3')">
            <div class="number">1000+</div>
            <div class="label">전문 인력</div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="achievement-item" @click="showPopup('achievement4')">
            <div class="number">A등급</div>
            <div class="label">건설업 등급</div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
        </div>
      </div>

      <!-- 혁신 기술 섹션 -->
      <div class="content-block">
        <h2>혁신 기술</h2>
        <div class="innovation-grid">
          <div class="innovation-item" @click="showPopup('bim')">
            <img src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="BIM 기술">
            <div class="innovation-content">
              <h3>BIM 기술</h3>
              <p>Building Information Modeling을 통한 정밀한 건설 계획</p>
            </div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="innovation-item" @click="showPopup('smart')">
            <img src="https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="스마트 건설">
            <div class="innovation-content">
              <h3>스마트 건설</h3>
              <p>IoT와 AI를 활용한 지능형 건설 시스템</p>
            </div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
          <div class="innovation-item" @click="showPopup('eco')">
            <img src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="친환경 건설">
            <div class="innovation-content">
              <h3>친환경 건설</h3>
              <p>지속가능한 건설을 위한 친환경 기술</p>
            </div>
            <div class="click-hint">클릭하여 자세히 보기</div>
          </div>
        </div>
      </div>
    </div>

    <!-- 팝업 모달 -->
    <div v-if="showPopupModal" class="popup-overlay" @click="closePopup">
      <div class="popup-content" @click.stop>
        <div class="popup-header">
          <h3>{{ currentPopup.title }}</h3>
          <button class="popup-close" @click="closePopup">×</button>
        </div>
        <div class="popup-body">
          <div class="popup-image" v-if="currentPopup.image">
            <img :src="currentPopup.image" :alt="currentPopup.title">
          </div>
          <div class="popup-text">
            <h4>{{ currentPopup.subtitle }}</h4>
            <p>{{ currentPopup.description }}</p>
            <ul class="popup-features" v-if="currentPopup.features">
              <li v-for="feature in currentPopup.features" :key="feature">
                {{ feature }}
              </li>
            </ul>
            <div class="popup-details" v-if="currentPopup.details">
              <p>{{ currentPopup.details }}</p>
            </div>
          </div>
        </div>
        <div class="popup-footer">
          <button class="popup-btn primary" @click="closePopup">확인</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const showPopupModal = ref(false)
const currentPopup = ref({})

const popupData = {
  philosophy: {
    title: '기업 철학',
    subtitle: '고객 만족과 사회 발전',
    description: '유진건설은 고객의 만족을 최우선으로 하며, 사회 발전에 기여하는 건설 서비스를 제공합니다.',
    features: [
      '고객 중심의 서비스 제공',
      '사회적 가치 창출',
      '지속가능한 발전 추구',
      '윤리적 건설 문화 정착'
    ]
  },
  vision: {
    title: '기업 비전',
    subtitle: '건설 산업의 선도자',
    description: '혁신적인 건설 기술과 창의적인 아이디어로 건설 산업의 새로운 패러다임을 제시합니다.',
    features: [
      '기술 혁신 선도',
      '품질 경쟁력 확보',
      '글로벌 시장 진출',
      '미래 건설 기술 개발'
    ]
  },
  innovation: {
    title: '기술 혁신',
    subtitle: '새로운 건설 패러다임',
    description: '최신 건설 기술과 디지털 솔루션을 접목하여 건설의 효율성과 안전성을 극대화합니다.',
    features: [
      'BIM 기술 도입',
      '스마트 건설 시스템',
      'AI 기반 품질 관리',
      '친환경 건축 자재'
    ]
  },
  construction1: {
    title: '현대적인 건축물',
    subtitle: '최신 건설 기술',
    description: '최신 건설 기술과 친환경 건축 자재를 활용하여 현대적이고 아름다운 건축물을 완성합니다.',
    image: 'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    features: [
      '친환경 건축 자재 사용',
      '에너지 효율성 극대화',
      '현대적 디자인 적용',
      '지진 내진 설계'
    ]
  },
  construction2: {
    title: '전문적인 시공',
    subtitle: '숙련된 전문가',
    description: '30년간 축적된 건설 노하우와 숙련된 전문가들이 정밀하고 안전한 시공을 진행합니다.',
    image: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    features: [
      '숙련된 기술진',
      '정밀한 품질 관리',
      '안전 우선 작업',
      '체계적인 공정 관리'
    ]
  },
  construction3: {
    title: '안전한 작업환경',
    subtitle: '안전 최우선',
    description: '안전을 최우선으로 하는 건설 현장에서 모든 작업원의 안전을 보장합니다.',
    image: 'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    features: [
      '안전 교육 실시',
      '보호구 착용 의무화',
      '정기 안전 점검',
      '응급 대응 시스템'
    ]
  },
  architecture: {
    title: '건축 공사',
    subtitle: '다양한 건축물 시공',
    description: '상업시설, 주거시설, 공공시설 등 다양한 용도의 건축물을 최고 품질로 시공합니다.',
    features: [
      '상업시설 건축',
      '주거시설 건축',
      '공공시설 건축',
      '문화시설 건축'
    ]
  },
  civil: {
    title: '토목 공사',
    subtitle: '사회기반시설 건설',
    description: '도로, 교량, 터널 등 국가와 지역의 발전을 위한 핵심 인프라를 건설합니다.',
    features: [
      '도로 및 고속도로',
      '교량 및 터널',
      '항만 및 공항',
      '수리 시설'
    ]
  },
  industrial: {
    title: '산업시설',
    subtitle: '산업 발전 기반',
    description: '공장, 발전소, 정유시설 등 산업 발전의 핵심이 되는 시설을 건설합니다.',
    features: [
      '제조업 시설',
      '발전소 시설',
      '정유 시설',
      '물류 시설'
    ]
  },
  housing: {
    title: '주택 개발',
    subtitle: '편리한 주거 환경',
    description: '아파트, 단독주택, 상가 등 다양한 주거 형태의 개발을 통해 삶의 질을 향상시킵니다.',
    features: [
      '아파트 단지',
      '단독주택',
      '상가 및 오피스',
      '복합단지'
    ]
  },
  achievement1: {
    title: '500+ 완공 프로젝트',
    subtitle: '축적된 경험과 실적',
    description: '30년간 다양한 건설 프로젝트를 성공적으로 완공하여 풍부한 경험과 노하우를 축적했습니다.',
    details: '주요 프로젝트: 서울타워, 강남 비즈니스 센터, 인천국제공항 제2터미널, 부산 해운대 마린시티 등'
  },
  achievement2: {
    title: '30년+ 건설 경험',
    subtitle: '오랜 역사와 전통',
    description: '1994년 설립 이후 30년간 건설 산업의 변화와 발전을 함께하며 신뢰할 수 있는 파트너로 성장했습니다.',
    details: '설립: 1994년, 본사: 서울특별시 강남구, 직원 수: 1,000명 이상'
  },
  achievement3: {
    title: '1000+ 전문 인력',
    subtitle: '최고의 전문가들',
    description: '건축, 토목, 전기, 기계 등 각 분야의 전문가들이 모여 최고 품질의 건설 서비스를 제공합니다.',
    details: '건축사: 150명, 토목기술사: 200명, 전기기술사: 100명, 기계기술사: 80명 등'
  },
  achievement4: {
    title: 'A등급 건설업 등급',
    subtitle: '최고 품질 인증',
    description: '건설업 등급 평가에서 최고 등급인 A등급을 받아 품질과 신뢰성을 인정받았습니다.',
    details: '평가 항목: 기술능력, 재무상태, 경영상태, 시공실적, 품질관리 등'
  },
  bim: {
    title: 'BIM 기술',
    subtitle: 'Building Information Modeling',
    description: '3D 모델링을 기반으로 건설 전 과정의 정보를 통합 관리하여 효율성과 정확성을 극대화합니다.',
    image: 'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    features: [
      '3D 모델링 기반 설계',
      '통합 정보 관리',
      '시공 과정 시뮬레이션',
      '유지보수 정보 제공'
    ]
  },
  smart: {
    title: '스마트 건설',
    subtitle: 'IoT와 AI 활용',
    description: '사물인터넷(IoT)과 인공지능(AI)을 활용하여 건설 현장의 효율성과 안전성을 혁신적으로 향상시킵니다.',
    image: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    features: [
      '실시간 현장 모니터링',
      '자동화된 장비 제어',
      'AI 기반 품질 검사',
      '스마트 안전 관리'
    ]
  },
  eco: {
    title: '친환경 건설',
    subtitle: '지속가능한 건설',
    description: '환경을 생각하는 친환경 건축 자재와 기술을 활용하여 미래 세대를 위한 지속가능한 건설을 실현합니다.',
    image: 'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
    features: [
      '친환경 건축 자재',
      '에너지 절약 설계',
      '재생 에너지 시스템',
      '자원 순환 건설'
    ]
  }
}

const showPopup = (type) => {
  currentPopup.value = popupData[type]
  showPopupModal.value = true
}

const closePopup = () => {
  showPopupModal.value = false
}
</script>

<style scoped>
.contents-section {
  padding: 80px 0;
  background: #f8f9fa;
}

.contents-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.content-block {
  margin-bottom: 80px;
}

.content-block h2 {
  text-align: center;
  color: #2c3e50;
  font-size: 36px;
  margin-bottom: 50px;
  position: relative;
}

.content-block h2::after {
  content: '';
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background: #3498db;
}

.content-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.content-item {
  background: white;
  padding: 40px 30px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
  transition: all 0.3s;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.content-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(52, 152, 219, 0.1), transparent);
  transition: left 0.5s;
}

.content-item:hover::before {
  left: 100%;
}

.content-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

.content-item .icon {
  font-size: 60px;
  margin-bottom: 20px;
}

.content-item h3 {
  color: #2c3e50;
  margin-bottom: 15px;
  font-size: 24px;
}

.content-item p {
  color: #7f8c8d;
  line-height: 1.6;
  margin-bottom: 20px;
}

.click-hint {
  color: #3498db;
  font-size: 14px;
  font-weight: 500;
  opacity: 0;
  transition: opacity 0.3s;
}

.content-item:hover .click-hint {
  opacity: 1;
}

/* 건설 현장 갤러리 스타일 */
.construction-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 25px;
}

.gallery-item {
  position: relative;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
  transition: all 0.3s;
  cursor: pointer;
}

.gallery-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

.gallery-item img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  transition: transform 0.3s;
}

.gallery-item:hover img {
  transform: scale(1.1);
}

.gallery-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(transparent, rgba(0,0,0,0.8));
  color: white;
  padding: 30px 20px 20px;
  transform: translateY(100%);
  transition: transform 0.3s;
}

.gallery-item:hover .gallery-overlay {
  transform: translateY(0);
}

.gallery-overlay h3 {
  margin: 0 0 10px 0;
  font-size: 20px;
}

.gallery-overlay p {
  margin: 0;
  font-size: 14px;
  opacity: 0.9;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 25px;
}

.project-card {
  background: white;
  padding: 30px 20px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
  transition: all 0.3s;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(52, 152, 219, 0.1), transparent);
  transition: left 0.5s;
}

.project-card:hover::before {
  left: 100%;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

.project-image {
  font-size: 50px;
  margin-bottom: 20px;
}

.project-card h3 {
  color: #2c3e50;
  margin-bottom: 15px;
  font-size: 20px;
}

.project-card p {
  color: #7f8c8d;
  line-height: 1.6;
  font-size: 14px;
  margin-bottom: 20px;
}

.achievements {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
}

.achievement-item {
  text-align: center;
  background: white;
  padding: 40px 20px;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
  transition: all 0.3s;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.achievement-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(52, 152, 219, 0.1), transparent);
  transition: left 0.5s;
}

.achievement-item:hover::before {
  left: 100%;
}

.achievement-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

.achievement-item .number {
  font-size: 48px;
  font-weight: bold;
  color: #3498db;
  margin-bottom: 10px;
}

.achievement-item .label {
  color: #7f8c8d;
  font-size: 16px;
  margin-bottom: 15px;
}

/* 혁신 기술 섹션 */
.innovation-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 30px;
}

.innovation-item {
  background: white;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
  transition: all 0.3s;
  cursor: pointer;
  position: relative;
}

.innovation-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(52, 152, 219, 0.1), transparent);
  transition: left 0.5s;
  z-index: 1;
}

.innovation-item:hover::before {
  left: 100%;
}

.innovation-item:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.2);
}

.innovation-item img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s;
}

.innovation-item:hover img {
  transform: scale(1.05);
}

.innovation-content {
  padding: 25px;
  position: relative;
  z-index: 2;
}

.innovation-content h3 {
  color: #2c3e50;
  margin-bottom: 15px;
  font-size: 22px;
}

.innovation-content p {
  color: #7f8c8d;
  line-height: 1.6;
  margin-bottom: 20px;
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

.popup-details {
  background: #f8f9fa;
  padding: 15px;
  border-radius: 8px;
  margin-top: 20px;
}

.popup-details p {
  margin: 0;
  color: #2c3e50;
  font-size: 14px;
  line-height: 1.6;
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
  .content-grid,
  .projects-grid,
  .achievements,
  .construction-gallery,
  .innovation-grid {
    grid-template-columns: 1fr;
  }
  
  .content-block h2 {
    font-size: 28px;
  }
  
  .gallery-item img {
    height: 200px;
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
