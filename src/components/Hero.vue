<template>
    <div class="hero-section" id="home">
      <!-- Arka plan gradient ve overlay -->
      <div class="hero-background">
        <div class="gradient-overlay"></div>
        <div class="pattern-overlay"></div>
      </div>
      
      <!-- Ana içerik -->
      <div class="hero-content">
        <div class="hero-text-section">
          <div class="hero-badge">
            <span class="badge-icon">🌟</span>
            <span class="badge-text">Türk Mutfağının En İyi Örnekleri</span>
          </div>
          
          <h1 class="hero-title">
            <span class="title-line">Geleneği</span>
            <span class="title-line highlight">Tadın</span>
            <span class="title-line">Lezzeti</span>
            <span class="title-line highlight">Sevin</span>
          </h1>
          
          <p class="hero-description">
            Otantik Türk mutfağının eşsiz lezzetlerini modern sunum teknikleriyle 
            buluşturan unutulmaz bir gastronomi deneyimi yaşayın.
          </p>
          
          <div class="hero-actions">
            <button class="btn-primary">
              <span class="btn-icon">🍽️</span>
              Menüyü Keşfet
            </button>
            <button class="btn-secondary">
              <span class="btn-icon">📞</span>
              Rezervasyon
            </button>
          </div>
          
          <div class="hero-stats">
            <div class="stat-item">
              <span class="stat-number">25+</span>
              <span class="stat-label">Yıllık Deneyim</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">100+</span>
              <span class="stat-label">Geleneksel Tarif</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">4.9</span>
              <span class="stat-label">Müşteri Puanı</span>
            </div>
          </div>
        </div>
        
        <div class="hero-image-section">
          <div class="image-container">
            <div class="image-card">
              <img src="@/assets/images/indian-food-eg.jpg" alt="Türk Yemekleri" class="hero-image" />
              <div class="image-overlay"></div>
            </div>
            <div class="floating-card card-1">
              <div class="card-icon">🥘</div>
              <div class="card-content">
                <h4>Geleneksel</h4>
                <p>Otantik tarifler</p>
              </div>
            </div>
            <div class="floating-card card-2">
              <div class="card-icon">👨‍🍳</div>
              <div class="card-content">
                <h4>Uzman Şef</h4>
                <p>Deneyimli ekip</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Scroll indicator -->
      <div class="scroll-indicator">
        <div class="scroll-arrow"></div>
        <span class="scroll-text">Keşfet</span>
      </div>
    </div>
</template>

<script setup>
</script>

<style scoped>
.hero-section {
  min-height: 100vh;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  background: linear-gradient(135deg, var(--primary-color) 0%, #c00914 50%, #a00711 100%);
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
}

.gradient-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(227, 10, 23, 0.9) 0%, rgba(192, 9, 20, 0.8) 50%, rgba(160, 7, 17, 0.9) 100%);
}

.pattern-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    radial-gradient(circle at 25% 25%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 75% 75%, rgba(244, 162, 97, 0.1) 0%, transparent 50%);
  animation: patternFloat 20s ease-in-out infinite;
}

@keyframes patternFloat {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(1deg); }
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 1400px;
  width: 100%;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-text-section {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 50px;
  padding: 0.75rem 1.5rem;
  width: fit-content;
  animation: badgeFloat 3s ease-in-out infinite;
}

@keyframes badgeFloat {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-5px); }
}

.badge-icon {
  font-size: 1.2rem;
}

.badge-text {
  color: var(--secondary-color);
  font-size: 0.9rem;
  font-weight: 500;
  font-family: 'Inter', sans-serif;
}

.hero-title {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin: 0;
}

.title-line {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 700;
  color: var(--secondary-color);
  line-height: 1.1;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  animation: titleSlideIn 1s ease-out forwards;
  opacity: 0;
  transform: translateX(-50px);
}

.title-line:nth-child(1) { animation-delay: 0.2s; }
.title-line:nth-child(2) { animation-delay: 0.4s; }
.title-line:nth-child(3) { animation-delay: 0.6s; }
.title-line:nth-child(4) { animation-delay: 0.8s; }

@keyframes titleSlideIn {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.highlight {
  background: linear-gradient(45deg, var(--accent-color), #E76F51);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  position: relative;
}

.highlight::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(45deg, var(--accent-color), #E76F51);
  border-radius: 2px;
}

.hero-description {
  font-size: 1.2rem;
  line-height: 1.6;
  color: rgba(255, 255, 255, 0.9);
  max-width: 500px;
  font-family: 'Inter', sans-serif;
  animation: fadeInUp 1s ease-out 1s forwards;
  opacity: 0;
  transform: translateY(30px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  animation: fadeInUp 1s ease-out 1.2s forwards;
  opacity: 0;
  transform: translateY(30px);
}

.btn-primary, .btn-secondary {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border: none;
  border-radius: 50px;
  font-size: 1rem;
  font-weight: 600;
  font-family: 'Inter', sans-serif;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  position: relative;
  overflow: hidden;
}

.btn-primary {
  background: var(--secondary-color);
  color: var(--primary-color);
  box-shadow: 0 8px 25px rgba(255, 255, 255, 0.3);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 12px 35px rgba(255, 255, 255, 0.4);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: var(--secondary-color);
  border: 2px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-3px);
  border-color: rgba(255, 255, 255, 0.5);
}

.btn-icon {
  font-size: 1.1rem;
}

.hero-stats {
  display: flex;
  gap: 2rem;
  margin-top: 1rem;
  animation: fadeInUp 1s ease-out 1.4s forwards;
  opacity: 0;
  transform: translateY(30px);
}

.stat-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.25rem;
}

.stat-number {
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--accent-color);
  font-family: 'Playfair Display', serif;
}

.stat-label {
  font-size: 0.8rem;
  color: rgba(255, 255, 255, 0.8);
  font-family: 'Inter', sans-serif;
  text-align: center;
}

.hero-image-section {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-container {
  position: relative;
  width: 100%;
  max-width: 500px;
}

.image-card {
  position: relative;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  animation: imageFloat 6s ease-in-out infinite;
}

@keyframes imageFloat {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-10px) rotate(1deg); }
}

.hero-image {
  width: 100%;
  height: 400px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(227, 10, 23, 0.2), rgba(244, 162, 97, 0.1));
}

.floating-card {
  position: absolute;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 1rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  display: flex;
  align-items: center;
  gap: 0.75rem;
  animation: cardFloat 4s ease-in-out infinite;
}

.card-1 {
  top: -20px;
  left: -30px;
  animation-delay: 0s;
}

.card-2 {
  bottom: -20px;
  right: -30px;
  animation-delay: 2s;
}

@keyframes cardFloat {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-8px) rotate(2deg); }
}

.card-icon {
  font-size: 1.5rem;
}

.card-content h4 {
  margin: 0;
  font-size: 0.9rem;
  font-weight: 600;
  color: var(--primary-color);
  font-family: 'Inter', sans-serif;
}

.card-content p {
  margin: 0;
  font-size: 0.7rem;
  color: #666;
  font-family: 'Inter', sans-serif;
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  color: var(--secondary-color);
  animation: scrollBounce 2s ease-in-out infinite;
  z-index: 3;
}

@keyframes scrollBounce {
  0%, 100% { transform: translateX(-50%) translateY(0px); }
  50% { transform: translateX(-50%) translateY(-10px); }
}

.scroll-arrow {
  width: 2px;
  height: 30px;
  background: var(--secondary-color);
  border-radius: 1px;
  position: relative;
}

.scroll-arrow::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: -3px;
  width: 8px;
  height: 8px;
  border-right: 2px solid var(--secondary-color);
  border-bottom: 2px solid var(--secondary-color);
  transform: rotate(45deg);
}

.scroll-text {
  font-size: 0.8rem;
  font-family: 'Inter', sans-serif;
  opacity: 0.8;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: center;
  }
  
  .hero-stats {
    justify-content: center;
  }
  
  .floating-card {
    display: none;
  }
}

@media (max-width: 768px) {
  .hero-content {
    padding: 0 1rem;
  }
  
  .hero-actions {
    flex-direction: column;
    align-items: center;
  }
  
  .btn-primary, .btn-secondary {
    width: 100%;
    max-width: 300px;
    justify-content: center;
  }
  
  .hero-stats {
    gap: 1rem;
  }
  
  .stat-item {
    flex: 1;
  }
  
  .hero-image {
    height: 300px;
  }
}

@media (max-width: 480px) {
  .hero-title {
    gap: 0.25rem;
  }
  
  .title-line {
    font-size: 2rem;
  }
  
  .hero-description {
    font-size: 1rem;
  }
  
  .hero-stats {
    flex-direction: column;
    gap: 1rem;
  }
  
  .stat-item {
    flex-direction: row;
    gap: 1rem;
  }
}
</style>