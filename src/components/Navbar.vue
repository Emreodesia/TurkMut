<template>
    <nav class="navbar" :class="{ 'navbar-scrolled': isScrolled }" id="home">
      <!-- Arka plan blur efekti -->
      <div class="navbar-background"></div>
      
      <div class="navbar-container">
        <!-- Logo bölümü -->
        <div class="logo-section">
          <RouterLink to="/" class="logo-link">
            <img src="@/assets/images/turkish-logo-simple.svg" alt="Türk Mutfağı Logo" class="logo-image" />
          </RouterLink>
        </div>

        <!-- Navigasyon linkleri -->
        <div class="nav-center">
          <div class="nav-links" :class="{ show: navLinksVisible }">
            <RouterLink to="/" class="nav-link">
              <span class="link-icon"></span>
              <span class="link-text">Ana Sayfa</span>
            </RouterLink>
            <RouterLink to="/menu" class="nav-link">
              <span class="link-icon"></span>
              <span class="link-text">Menü</span>
            </RouterLink>
            <RouterLink to="/contact" class="nav-link">
              <span class="link-icon"></span>
              <span class="link-text">İletişim</span>
            </RouterLink>
          </div>
        </div>

        <!-- Sağ taraf - Butonlar -->
        <div class="nav-right">
          <button @click="redirect" class="reservation-btn">
            <span class="btn-icon">📅</span>
            <span class="btn-text">Masa Rezervasyonu</span>
          </button>
          
          <!-- Mobil menü butonu -->
          <button @click="toggleNavLinks" class="mobile-menu-btn" :class="{ active: navLinksVisible }">
            <span class="hamburger-line"></span>
            <span class="hamburger-line"></span>
            <span class="hamburger-line"></span>
          </button>
        </div>
      </div>

      <!-- Mobil menü overlay -->
      <div class="mobile-overlay" :class="{ show: navLinksVisible }" @click="toggleNavLinks"></div>
    </nav>
</template>

<script setup>
    import { ref, onMounted, onUnmounted } from 'vue';
    import { RouterLink, useRouter } from 'vue-router';
    
    const navLinksVisible = ref(false);
    const isScrolled = ref(false);
    const router = useRouter();

    const toggleNavLinks = () => {
        navLinksVisible.value = !navLinksVisible.value;
    }

    const redirect = () => {
        router.push('/form');
    }

    const handleScroll = () => {
        isScrolled.value = window.scrollY > 50;
    }

    onMounted(() => {
        window.addEventListener('scroll', handleScroll);
    })

    onUnmounted(() => {
        window.removeEventListener('scroll', handleScroll);
    })
</script>

<style scoped>
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    transition: all 0.3s ease;
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
}

.navbar-background {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(135deg, rgba(227, 10, 23, 0.95) 0%, rgba(192, 9, 20, 0.9) 100%);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.navbar-scrolled {
    background: rgba(227, 10, 23, 0.98);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}

.navbar-container {
    position: relative;
    z-index: 2;
    max-width: 1400px;
    margin: 0 auto;
    padding: 1rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Logo Styles */
.logo-section {
    flex-shrink: 0;
}

.logo-link {
    display: block;
    text-decoration: none;
}

.logo-image {
    width: 160px;
    height: auto;
    transition: all 0.3s ease;
}

.logo-link:hover .logo-image {
    transform: scale(1.05);
    filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.2));
}

/* Navigation Center */
.nav-center {
    flex: 1;
    display: flex;
    justify-content: center;
}

.nav-links {
    display: flex;
    gap: 0;
    align-items: center;
    list-style: none;
    margin: 0;
    padding: 0;
}

.nav-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.25rem;
    padding: 0.75rem 1.5rem;
    color: var(--secondary-color);
    text-decoration: none;
    border-radius: 12px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.nav-link::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 12px;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.nav-link:hover::before {
    opacity: 1;
}

.nav-link:hover {
    transform: translateY(-2px);
    color: var(--accent-color);
}

.link-icon {
    font-size: 1.2rem;
    transition: transform 0.3s ease;
}

.nav-link:hover .link-icon {
    transform: scale(1.2);
}

.link-text {
    font-size: 0.9rem;
    font-weight: 500;
    font-family: 'Inter', sans-serif;
    transition: all 0.3s ease;
}

/* Right Section */
.nav-right {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.reservation-btn {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    background: linear-gradient(45deg, var(--secondary-color), #f8f9fa);
    color: var(--primary-color);
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 25px;
    font-size: 0.9rem;
    font-weight: 600;
    font-family: 'Inter', sans-serif;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(255, 255, 255, 0.3);
    position: relative;
    overflow: hidden;
}

.reservation-btn::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
    transition: left 0.5s ease;
}

.reservation-btn:hover::before {
    left: 100%;
}

.reservation-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(255, 255, 255, 0.4);
}

.btn-icon {
    font-size: 1rem;
}

.btn-text {
    font-weight: 600;
}

/* Mobile Menu Button */
.mobile-menu-btn {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    width: 30px;
    height: 25px;
    background: transparent;
    border: none;
    cursor: pointer;
    padding: 0;
    z-index: 1001;
}

.hamburger-line {
    width: 100%;
    height: 3px;
    background: var(--secondary-color);
    border-radius: 2px;
    transition: all 0.3s ease;
    transform-origin: center;
}

.mobile-menu-btn.active .hamburger-line:nth-child(1) {
    transform: rotate(45deg) translate(6px, 6px);
}

.mobile-menu-btn.active .hamburger-line:nth-child(2) {
    opacity: 0;
}

.mobile-menu-btn.active .hamburger-line:nth-child(3) {
    transform: rotate(-45deg) translate(6px, -6px);
}

/* Mobile Overlay */
.mobile-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(10px);
    z-index: 999;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
}

.mobile-overlay.show {
    opacity: 1;
    visibility: visible;
}

/* Responsive Design */
@media (max-width: 1024px) {
    .navbar-container {
        padding: 1rem 1.5rem;
    }
    
    .logo-image {
        width: 140px;
    }
    
    .nav-links {
        gap: 0.5rem;
    }
    
    .nav-link {
        padding: 0.5rem 1rem;
    }
    
    .link-text {
        font-size: 0.8rem;
    }
}

@media (max-width: 768px) {
    .nav-center {
        display: none;
    }
    
    .mobile-menu-btn {
        display: flex;
    }
    
    .nav-links {
        position: fixed;
        top: 0;
        right: -100%;
        width: 280px;
        height: 100vh;
        background: linear-gradient(135deg, var(--primary-color) 0%, #c00914 100%);
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        transition: right 0.3s ease;
        z-index: 1000;
        box-shadow: -10px 0 30px rgba(0, 0, 0, 0.3);
    }
    
    .nav-links.show {
        right: 0;
    }
    
    .nav-link {
        flex-direction: row;
        gap: 1rem;
        padding: 1rem 2rem;
        width: 80%;
        justify-content: flex-start;
        border-radius: 15px;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px);
    }
    
    .nav-link:hover {
        background: rgba(255, 255, 255, 0.2);
        transform: translateX(10px);
    }
    
    .link-icon {
        font-size: 1.5rem;
    }
    
    .link-text {
        font-size: 1.1rem;
        font-weight: 600;
    }
    
    .reservation-btn {
        padding: 0.6rem 1.2rem;
        font-size: 0.8rem;
    }
    
    .btn-text {
        display: none;
    }
}

@media (max-width: 480px) {
    .navbar-container {
        padding: 0.75rem 1rem;
    }
    
    .logo-image {
        width: 120px;
    }
    
    .nav-links {
        width: 100%;
    }
    
    .nav-link {
        width: 90%;
        padding: 1.2rem 2rem;
    }
    
    .link-text {
        font-size: 1rem;
    }
    
    .reservation-btn {
        padding: 0.5rem 1rem;
    }
}

/* Animation for navbar appearance */
@keyframes slideDown {
    from {
        transform: translateY(-100%);
        opacity: 0;
    }
    to {
        transform: translateY(0);
        opacity: 1;
    }
}

.navbar {
    animation: slideDown 0.5s ease-out;
}

/* Hover effects for better UX */
.nav-link:active {
    transform: scale(0.95);
}

.reservation-btn:active {
    transform: scale(0.95);
}
</style>
