<script setup>
    import Grid from '@/components/Grid.vue'
    import gridImg1 from '@/assets/images/grid-img1.jpg'
    import gridImg2 from '@/assets/images/grid-img2.jpg'
    import gridImg3 from '@/assets/images/grid-img3.jpg'
</script>

<template>
    <div class="about-section">
      <!-- Arka plan -->
      <div class="about-background">
        <div class="background-pattern"></div>
      </div>
      
      <!-- Ana içerik -->
      <div class="about-container">
        <!-- Başlık bölümü -->
        <div class="about-header">
          <div class="section-badge">
            <span class="badge-icon">🍽️</span>
            <span class="badge-text">Hakkımızda</span>
          </div>
          <h2 class="section-title">
            Türk Mutfağının <span class="highlight">Eşsiz</span> Lezzetleri
          </h2>
          <p class="section-description">
            Geleneksel tarifler ve modern sunum tekniklerini harmanlayarak, 
            size unutulmaz bir gastronomi deneyimi sunuyoruz.
          </p>
        </div>
        
        <!-- Kartlar grid -->
        <div class="about-grid">
          <div class="about-card card-1">
            <div class="card-image">
              <img :src="gridImg1" alt="Geleneksel Lezzetler" />
              <div class="image-overlay"></div>
            </div>
            <div class="card-content">
              <div class="card-icon">🌟</div>
              <h3>Geleneksel Lezzetler</h3>
              <p>
                Türk Mutfağı'nın eşsiz lezzetlerini keşfetmek için hoş geldiniz. 
                Geleneksel tarifler ve modern sunum teknikleriyle unutulmaz bir 
                yemek deneyimi yaşayın.
              </p>
              <div class="card-features">
                <span class="feature">Otantik Tarifler</span>
                <span class="feature">Geleneksel Yöntemler</span>
                <span class="feature">Kaliteli Malzemeler</span>
              </div>
            </div>
          </div>
          
          <div class="about-card card-2">
            <div class="card-image">
              <img :src="gridImg2" alt="Uzman Şefler" />
              <div class="image-overlay"></div>
            </div>
            <div class="card-content">
              <div class="card-icon">👨‍🍳</div>
              <h3>Uzman Şefler</h3>
              <p>
                Uzman şeflerimiz, Türkiye'nin zengin mutfak kültürünü yansıtan 
                otantik tarifleri modern dokunuşlarla harmanlayarak özel bir 
                menü hazırlar.
              </p>
              <div class="card-features">
                <span class="feature">Deneyimli Ekip</span>
                <span class="feature">Yaratıcı Sunum</span>
                <span class="feature">Sürekli İnovasyon</span>
              </div>
            </div>
          </div>
          
          <div class="about-card card-3">
            <div class="card-image">
              <img :src="gridImg3" alt="Sıcak Atmosfer" />
              <div class="image-overlay"></div>
            </div>
            <div class="card-content">
              <div class="card-icon">🏠</div>
              <h3>Sıcak Atmosfer</h3>
              <p>
                Sıcak ve samimi atmosferimizde, Türk misafirperverliğinin en 
                güzel örneklerini yaşayarak unutulmaz anılar biriktirin.
              </p>
              <div class="card-features">
                <span class="feature">Samimi Ortam</span>
                <span class="feature">Misafirperverlik</span>
                <span class="feature">Unutulmaz Anılar</span>
              </div>
            </div>
          </div>
        </div>
        
        <!-- İstatistikler -->
        <div class="about-stats">
          <div class="stat-card">
            <div class="stat-icon">🎯</div>
            <div class="stat-number">15+</div>
            <div class="stat-label">Yıllık Deneyim</div>
          </div>
          <div class="stat-card">
            <div class="stat-icon">🍽️</div>
            <div class="stat-number">150+</div>
            <div class="stat-label">Geleneksel Tarif</div>
          </div>
          <div class="stat-card">
            <div class="stat-icon">⭐</div>
            <div class="stat-number">4.9</div>
            <div class="stat-label">Müşteri Puanı</div>
          </div>
          <div class="stat-card">
            <div class="stat-icon">👥</div>
            <div class="stat-number">10K+</div>
            <div class="stat-label">Mutlu Müşteri</div>
          </div>
        </div>
      </div>
    </div>
</template>

<style scoped>
.about-section {
  position: relative;
  padding: 6rem 0;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 50%, #dee2e6 100%);
  overflow: hidden;
}

.about-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
}

.background-pattern {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    radial-gradient(circle at 20% 20%, rgba(227, 10, 23, 0.05) 0%, transparent 50%),
    radial-gradient(circle at 80% 80%, rgba(244, 162, 97, 0.05) 0%, transparent 50%);
  animation: patternMove 30s ease-in-out infinite;
}

@keyframes patternMove {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-30px) rotate(2deg); }
}

.about-container {
  position: relative;
  z-index: 2;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
}

.about-header {
  text-align: center;
  margin-bottom: 4rem;
  animation: fadeInUp 1s ease-out forwards;
  opacity: 0;
  transform: translateY(30px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.section-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(45deg, var(--primary-color), #c00914);
  color: var(--secondary-color);
  border-radius: 50px;
  padding: 0.75rem 1.5rem;
  margin-bottom: 1.5rem;
  box-shadow: 0 8px 25px rgba(227, 10, 23, 0.3);
  animation: badgePulse 3s ease-in-out infinite;
}

@keyframes badgePulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

.badge-icon {
  font-size: 1.2rem;
}

.badge-text {
  font-size: 0.9rem;
  font-weight: 600;
  font-family: 'Inter', sans-serif;
}

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.5rem, 5vw, 3.5rem);
  font-weight: 700;
  color: var(--dark-color);
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.highlight {
  background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
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
  background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
  border-radius: 2px;
}

.section-description {
  font-size: 1.2rem;
  line-height: 1.6;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
  font-family: 'Inter', sans-serif;
}

.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2.5rem;
  margin-bottom: 4rem;
}

.about-card {
  background: var(--secondary-color);
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.1);
  transition: all 0.4s ease;
  animation: cardSlideIn 1s ease-out forwards;
  opacity: 0;
  transform: translateY(50px);
}

.about-card:nth-child(1) { animation-delay: 0.2s; }
.about-card:nth-child(2) { animation-delay: 0.4s; }
.about-card:nth-child(3) { animation-delay: 0.6s; }

@keyframes cardSlideIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.about-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 25px 80px rgba(0, 0, 0, 0.15);
}

.card-image {
  position: relative;
  height: 250px;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.about-card:hover .card-image img {
  transform: scale(1.1);
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(227, 10, 23, 0.3), rgba(244, 162, 97, 0.2));
  opacity: 0;
  transition: opacity 0.4s ease;
}

.about-card:hover .image-overlay {
  opacity: 1;
}

.card-content {
  padding: 2rem;
}

.card-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  display: block;
}

.card-content h3 {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--dark-color);
  margin-bottom: 1rem;
}

.card-content p {
  font-size: 1rem;
  line-height: 1.6;
  color: #666;
  margin-bottom: 1.5rem;
  font-family: 'Inter', sans-serif;
}

.card-features {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.feature {
  background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
  color: var(--secondary-color);
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
  font-family: 'Inter', sans-serif;
}

.about-stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  animation: fadeInUp 1s ease-out 1s forwards;
  opacity: 0;
  transform: translateY(30px);
}

.stat-card {
  background: var(--secondary-color);
  border-radius: 15px;
  padding: 2rem;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.stat-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.15);
  border-color: var(--accent-color);
}

.stat-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  display: block;
}

.stat-number {
  font-family: 'Playfair Display', serif;
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--primary-color);
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  color: #666;
  font-family: 'Inter', sans-serif;
  font-weight: 500;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .about-grid {
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .about-stats {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .about-section {
    padding: 4rem 0;
  }
  
  .about-container {
    padding: 0 1rem;
  }
  
  .about-header {
    margin-bottom: 3rem;
  }
  
  .section-title {
    font-size: 2.5rem;
  }
  
  .section-description {
    font-size: 1.1rem;
  }
  
  .about-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .about-stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
  
  .stat-card {
    padding: 1.5rem;
  }
  
  .stat-number {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .about-section {
    padding: 3rem 0;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .section-description {
    font-size: 1rem;
  }
  
  .card-content {
    padding: 1.5rem;
  }
  
  .about-stats {
    grid-template-columns: 1fr;
  }
  
  .stat-card {
    padding: 1.5rem;
  }
}
</style>