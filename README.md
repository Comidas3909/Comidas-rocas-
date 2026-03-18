# Comidas-rocas-<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mundo de Sabores - Comida Colorida</title>
    <style>
        /* Reset y estilos base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #fff;
            overflow-x: hidden;
        }

        /* Fondo animado con gradiente */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff6b6b, #feca57, #48dbfb, #ff9ff3, #54a0ff, #5f27cd);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            z-index: -1;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Header */
        header {
            background: rgba(0,0,0,0.3);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b6b, #feca57);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            transform: translateY(-3px);
            text-shadow: 0 0 10px rgba(255,255,255,0.8);
        }

        /* Sección Hero */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 0 2rem;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, #feca57, #ff6b6b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 20px #fff); }
            to { filter: drop-shadow(0 0 30px #feca57); }
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 3rem;
            background: linear-gradient(45deg, #ff6b6b, #feca57);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255,107,107,0.4);
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(255,107,107,0.6);
        }

        /* Sección de Platos */
        .plates {
            padding: 100px 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 4rem;
            background: linear-gradient(45deg, #48dbfb, #54a0ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .plates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
        }

        .plate-card {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            transition: all 0.4s ease;
            border: 1px solid rgba(255,255,255,0.2);
            position: relative;
            overflow: hidden;
        }

        .plate-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .plate-card:hover::before {
            left: 100%;
        }

        .plate-card:hover {
            transform: translateY(-15px) scale(1.05);
            background: rgba(255,255,255,0.2);
        }

        .plate-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        .plate-card h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: #feca57;
        }

        .plate-card p {
            opacity: 0.9;
            margin-bottom: 1.5rem;
        }

        /* Footer */
        footer {
            background: rgba(0,0,0,0.5);
            backdrop-filter: blur(10px);
            text-align: center;
            padding: 3rem 2rem;
            margin-top: 5rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .nav-links {
                display: none;
            }
            
            .plates-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animaciones de entrada */
        .fade-in {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">🍔 Mundo de Sabores</div>
            <ul class="nav-links">
                <li><a href="#home">Inicio</a></li>
                <li><a href="#plates">Platos</a></li>
                <li><a href="#contact">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content fade-in">
            <h1>¡Descubre el Mundo de la Comida Colorida! 🌈🍕</h1>
            <p>Sabores intensos, colores vibrantes y platos irresistibles que harán que tus papilas gustativas exploten de emoción</p>
            <a href="#plates" class="cta-button">¡Explora Nuestros Platos! 🚀</a>
        </div>
    </section>

    <section id="plates" class="plates">
        <h2 class="section-title fade-in">Nuestros Platos Estrella ✨</h2>
        <div class="plates-grid">
            <div class="plate-card fade-in">
                <div class="plate-icon">🍔</div>
                <h3>Hamburguesa Explosiva</h3>
                <p>Carne jugosa, queso derretido, vegetales crujientes y salsas secretas en un pan artesanal. ¡Puro sabor americano!</p>
            </div>
            <div class="plate-card fade-in">
                <div class="plate-icon">🍣</div>
                <h3>Sushi Arcoíris</h3>
                <p>Selección premium de pescados frescos, aguacate cremoso y arroz perfecto. Cada bocado es una explosión de sabor japonés.</p>
            </div>
            <div class="plate-card fade-in">
                <div class="plate-icon">🌮</div>
                <h3>Tacos Mexicanos</h3>
                <p>Tortillas calientes rellenas de carne asada, cilantro fresco, cebolla y salsa picante. ¡Auténtico sabor mexicano!</p>
            </div>
            <div class="plate-card fade-in">
                <div class="plate-icon">🍝</div>
                <h3>Pasta Tricolor</h3>
                <p>Pasta fresca con salsa de tomate, pesto y queso crema. Tres colores, tres sabores increíbles en un solo plato.</p>
            </div>
            <div class="plate-card fade-in">
                <div class="plate-icon">🍕</div>
                <h3>Pizza Volcán</h3>
                <p>Masa crujiente, salsa especial, múltiples quesos y toppings que hacen erupción de sabor en tu boca.</p>
            </div>
            <div class="plate-card fade-in">
                <div class="plate-icon">🍦</div>
                <h3>Helado Arcoíris</h3>
                <p>Seis sabores diferentes en una sola copa. Delicioso final para cualquier comida espectacular.</p>
            </div>
        </div>
    </section>

    <footer id="contact">
        <h3>¿Listo para probar estos sabores increíbles?</h3>
        <p>Contáctanos: sabor@mundode sabores.com | +1 234 567 890</p>
        <p>&copy; 2024 Mundo de Sabores. Todos los derechos reservados. 🌟</p>
    </footer>

    <script>
        // Animación de scroll para fade-in
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Smooth scroll para navegación
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Efecto parallax sutil
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.hero');
            if (parallax) {
                parallax.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>
