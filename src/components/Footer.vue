<script setup>
</script>

<template>
     <div class="footer">
          <div class="footer-content">
               <!-- Logo ve Açıklama Bölümü -->
               <div class="footer-section brand-section">
                    <div class="logo-container">
                         <img src="@/assets/images/turkish-logo-simple.svg" alt="Türk Mutfağı Logo" class="footer-logo">
                         <h3>Türk Mutfağı</h3>
                    </div>
                    <p class="brand-description">
                         Geleneksel Türk lezzetlerini modern sunum teknikleriyle buluşturan eşsiz deneyim.
                    </p>
                    
               </div>

               <!-- İletişim Bilgileri -->
               <div class="footer-section contact-section">
                    <h4>İletişim</h4>
                    <div class="contact-item">
                         <div class="contact-icon">📍</div>
                         <div class="contact-text">
                              <p>Sultanahmet Meydanı, Fatih</p>
                              <p>İstanbul, Türkiye - 34122</p>
                         </div>
                    </div>
                    <div class="contact-item">
                         <div class="contact-icon">📞</div>
                         <div class="contact-text">
                              <a href="tel:+902121234567">(+90) 212 123 45 67</a>
                         </div>
                    </div>
                    
               </div>

               <!-- Çalışma Saatleri -->
               <div class="footer-section hours-section">
                    <h4>Çalışma Saatleri</h4>
                    <div class="hours-item">
                         <span class="day">Pazartesi - Cuma</span>
                         <span class="time">11:00 - 22:00</span>
                    </div>
                    <div class="hours-item">
                         <span class="day">Cumartesi</span>
                         <span class="time">11:00 - 23:00</span>
                    </div>
                    <div class="hours-item">
                         <span class="day">Pazar</span>
                         <span class="time">11:00 - 23:00</span>
                    </div>
                    
               </div>
          </div>

          <!-- Alt Çizgi -->
          <div class="footer-bottom">
               <div class="footer-line"></div>
               <p class="copyright">
                    © 2024 Türk Mutfağı. Tüm hakları saklıdır. | 
                    <a href="#">Gizlilik Politikası</a> | 
                    <a href="#">Kullanım Şartları</a>
               </p>
          </div>
     </div>
</template>

<style scoped>
.footer {
     background: linear-gradient(135deg, var(--primary-color) 0%, #c00914 50%, #a00711 100%);
     color: var(--secondary-color);
     padding: 0;
     position: relative;
     overflow: hidden;
}

.footer::before {
     content: '';
     position: absolute;
     top: 0;
     left: 0;
     right: 0;
     height: 3px;
     background: linear-gradient(90deg, var(--secondary-color), var(--accent-color), var(--secondary-color));
     animation: shimmer 3s ease-in-out infinite;
}

@keyframes shimmer {
     0%, 100% { opacity: 0.8; }
     50% { opacity: 1; }
}

.footer-content {
     max-width: 1200px;
     margin: 0 auto;
     padding: 4rem 2rem 2rem;
     display: grid;
     grid-template-columns: 2fr 1fr 1fr;
     gap: 3rem;
}

/* Brand Section */
.brand-section {
     display: flex;
     flex-direction: column;
     gap: 1.5rem;
}

.logo-container {
     display: flex;
     align-items: center;
     gap: 1rem;
     margin-bottom: 1rem;
}

.footer-logo {
     width: 120px;
     height: auto;
     filter: brightness(0) invert(1);
     transition: transform 0.3s ease;
}

.footer-logo:hover {
     transform: scale(1.05);
}

.logo-container h3 {
     font-family: 'Playfair Display', serif;
     font-size: 2.2rem;
     font-weight: 700;
     color: var(--secondary-color);
     margin: 0;
     text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.brand-description {
     font-size: 1.1rem;
     line-height: 1.6;
     color: rgba(255, 255, 255, 0.9);
     max-width: 350px;
     font-weight: 400;
}

.social-icons {
     display: flex;
     gap: 1rem;
     margin-top: 1rem;
}

.social-icon {
     display: flex;
     align-items: center;
     justify-content: center;
     width: 45px;
     height: 45px;
     background: rgba(255, 255, 255, 0.1);
     border-radius: 50%;
     transition: all 0.3s ease;
     border: 1px solid rgba(255, 255, 255, 0.2);
}

.social-icon:hover {
     background: var(--primary-color);
     transform: translateY(-3px);
     box-shadow: 0 8px 25px rgba(227, 10, 23, 0.4);
}

.social-icon img {
     width: 20px;
     height: 20px;
     filter: brightness(0) invert(1);
}

/* Contact Section */
.contact-section h4,
.hours-section h4 {
     font-family: 'Playfair Display', serif;
     font-size: 1.6rem;
     font-weight: 600;
     margin-bottom: 1.5rem;
     color: var(--secondary-color);
     position: relative;
     text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.contact-section h4::after,
.hours-section h4::after {
     content: '';
     position: absolute;
     bottom: -8px;
     left: 0;
     width: 50px;
     height: 3px;
     background: var(--secondary-color);
     border-radius: 2px;
     box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.contact-item {
     display: flex;
     align-items: flex-start;
     gap: 1rem;
     margin-bottom: 1.2rem;
     padding: 1rem;
     border-radius: 10px;
     transition: all 0.3s ease;
     background: rgba(255, 255, 255, 0.1);
     border: 1px solid rgba(255, 255, 255, 0.2);
}

.contact-item:hover {
     background: rgba(255, 255, 255, 0.15);
     transform: translateY(-2px);
     box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.contact-icon {
     display: flex;
     align-items: center;
     justify-content: center;
     width: 40px;
     height: 40px;
     background: var(--secondary-color);
     border-radius: 50%;
     flex-shrink: 0;
     color: var(--primary-color);
     font-size: 18px;
     box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.contact-text p,
.contact-text a {
     margin: 0;
     font-size: 1rem;
     line-height: 1.4;
     color: var(--secondary-color);
     text-decoration: none;
     transition: color 0.3s ease;
     font-weight: 500;
}

.contact-text a:hover {
     color: var(--accent-color);
     text-shadow: 0 0 8px rgba(244, 162, 97, 0.5);
}

/* Hours Section */
.hours-item {
     display: flex;
     justify-content: space-between;
     align-items: center;
     padding: 1rem;
     margin-bottom: 0.5rem;
     border-radius: 8px;
     transition: all 0.3s ease;
     background: rgba(255, 255, 255, 0.1);
     border: 1px solid rgba(255, 255, 255, 0.15);
}

.hours-item:hover {
     background: rgba(255, 255, 255, 0.15);
     transform: translateX(5px);
     box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.day {
     font-weight: 600;
     color: var(--secondary-color);
     font-size: 1rem;
}

.time {
     font-weight: 700;
     color: var(--accent-color);
     font-size: 1rem;
     text-shadow: 0 0 8px rgba(244, 162, 97, 0.3);
}

.special-notice {
     margin-top: 1.5rem;
     padding: 1.2rem;
     background: rgba(244, 162, 97, 0.2);
     border-radius: 10px;
     border: 2px solid var(--accent-color);
     box-shadow: 0 4px 15px rgba(244, 162, 97, 0.2);
}

.special-notice p {
     margin: 0;
     font-size: 1rem;
     color: var(--secondary-color);
     font-weight: 600;
     text-align: center;
}

/* Footer Bottom */
.footer-bottom {
     padding: 2rem;
     text-align: center;
     background: rgba(0, 0, 0, 0.2);
     backdrop-filter: blur(10px);
}

.footer-line {
     height: 2px;
     background: linear-gradient(90deg, transparent, var(--secondary-color), transparent);
     margin-bottom: 1.5rem;
     box-shadow: 0 2px 8px rgba(255, 255, 255, 0.3);
}

.copyright {
     font-size: 0.95rem;
     color: rgba(255, 255, 255, 0.8);
     margin: 0;
     font-weight: 400;
}

.copyright a {
     color: var(--accent-color);
     text-decoration: none;
     transition: all 0.3s ease;
     font-weight: 500;
}

.copyright a:hover {
     color: var(--secondary-color);
     text-shadow: 0 0 8px rgba(255, 255, 255, 0.5);
}

/* Responsive Design */
@media (max-width: 768px) {
     .footer-content {
          grid-template-columns: 1fr;
          gap: 2rem;
          padding: 3rem 1.5rem 1.5rem;
     }

     .brand-section {
          text-align: center;
     }

     .logo-container {
          justify-content: center;
     }

     .brand-description {
          max-width: 100%;
     }

     .social-icons {
          justify-content: center;
     }

     .contact-item,
     .hours-item {
          padding: 0.8rem;
     }

     .footer-bottom {
          padding: 1.5rem 1rem;
     }
}

@media (max-width: 480px) {
     .footer-content {
          padding: 2rem 1rem 1rem;
     }

     .logo-container h3 {
          font-size: 1.8rem;
     }

     .contact-section h4,
     .hours-section h4 {
          font-size: 1.4rem;
     }

     .contact-icon {
          width: 35px;
          height: 35px;
          font-size: 16px;
     }
}
</style> 