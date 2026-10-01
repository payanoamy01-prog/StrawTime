# StrawTime
#vivetustrawtime[strawtimee.html](https://github.com/user-attachments/files/32881224/strawtimee.html)

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StrawTime</title>
    <!-- Icono de fresa en la pestaña -->
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='.9em' font-size='90'%3E🍓%3C/text%3E%3C/svg%3E">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', 'Times New Roman', serif;
            background-color: #fff0f5;
            color: #3a2e2e;
            line-height: 1.6;
            position: relative;
            overflow-x: hidden;
        }

        /* Logo de fondo con brillo sutil */
        .fondo-logo {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 450px;
            height: 450px;
            background-image: url('logo-strawtime.jpg');
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            opacity: 0.06;
            z-index: 0;
            pointer-events: none;
            animation: suaveBrillo 8s ease-in-out infinite;
        }

        @keyframes suaveBrillo {
            0%, 100% { opacity: 0.05; }
            50% { opacity: 0.08; }
        }

        /* Barra de navegación */
        nav {
            position: relative;
            z-index: 10;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 60px;
            background-color: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 20px rgba(209, 96, 116, 0.08);
        }

        .nav-links {
            display: flex;
            gap: 35px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #5a4a4a;
            font-size: 15px;
            letter-spacing: 0.7px;
            transition: color 0.3s ease, transform 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: #f48fb1;
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: #d16074;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .logo-texto {
            font-size: 28px;
            font-weight: 600;
            letter-spacing: 3px;
            color: #2c2c2c;
            font-style: italic;
        }

        /* Sección principal */
        .hero {
            position: relative;
            z-index: 5;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            min-height: 85vh;
            padding: 40px 20px;
        }

        .hero-contenido {
            max-width: 700px;
            animation: entradaSuave 1s ease-out;
        }

        @keyframes entradaSuave {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero h1 {
            font-size: 64px;
            letter-spacing: 4px;
            margin-bottom: 15px;
            color: #2c2c2c;
        }

        .eslogan {
            font-size: 22px;
            color: #d16074;
            font-style: italic;
            margin-bottom: 30px;
        }

        .hero p {
            font-size: 17px;
            color: #6b5e5e;
            margin-bottom: 40px;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
        }

        .boton-principal {
            padding: 14px 40px;
            background: linear-gradient(135deg, #f8c8d0 0%, #f4a4b4 100%);
            border: none;
            border-radius: 50px;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            letter-spacing: 1px;
            box-shadow: 0 4px 15px rgba(209, 96, 116, 0.2);
        }

        .boton-principal a {
            text-decoration: none;
            color: #2c2c2c;
            font-weight: 500;
        }

        .boton-principal:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(209, 96, 116, 0.25);
        }

        /* Secciones generales */
        section {
            position: relative;
            z-index: 5;
            padding: 70px 40px;
            max-width: 1100px;
            margin: 0 auto;
        }

        .titulo-seccion {
            text-align: center;
            font-size: 32px;
            letter-spacing: 2px;
            margin-bottom: 10px;
            color: #2c2c2c;
        }

        .subtitulo-seccion {
            text-align: center;
            color: #d16074;
            font-style: italic;
            margin-bottom: 50px;
            font-size: 18px;
        }

        /* Historia */
        .historia-caja {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 8px 30px rgba(209, 96, 116, 0.08);
            position: relative;
            overflow: hidden;
        }

        .historia-caja::before {
            content: '🍓';
            position: absolute;
            top: 20px;
            right: 30px;
            font-size: 40px;
            opacity: 0.15;
        }

        .historia-texto {
            color: #5a4a4a;
            font-size: 17px;
            line-height: 1.8;
            text-align: center;
        }

        /* Catálogo de productos */
        .catalogo {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }

        .producto {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 25px;
            text-align: center;
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .producto::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #f48fb1, #d16074, #f48fb1);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }

        .producto:hover::before {
            transform: scaleX(1);
        }

        .producto:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 35px rgba(209, 96, 116, 0.15);
        }

        .producto-imagen {
            width: 100%;
            height: 220px;
            object-fit: cover;
            border-radius: 16px;
            margin-bottom: 20px;
            border: 3px solid #ffe6ee;
            transition: transform 0.3s ease;
        }

        .producto:hover .producto-imagen {
            transform: scale(1.03);
        }

        .producto h3 {
            font-size: 20px;
            color: #2c2c2c;
            margin-bottom: 10px;
            letter-spacing: 1px;
        }

        .producto p {
            color: #7a6a6a;
            font-size: 15px;
            margin-bottom: 15px;
        }

        .precio {
            font-size: 24px;
            font-weight: 700;
            color: #d16074;
            letter-spacing: 1px;
        }

        /* Formulario de Pedido */
        .formulario-caja {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 8px 30px rgba(209, 96, 116, 0.08);
            max-width: 550px;
            margin: 0 auto;
        }

        .grupo-form {
            margin-bottom: 25px;
        }

        .grupo-form label {
            display: block;
            margin-bottom: 8px;
            color: #5a4a4a;
            font-weight: 500;
        }

        .grupo-form input, .grupo-form select, .grupo-form textarea {
            width: 100%;
            padding: 14px 18px;
            border: 2px solid #f0d9e0;
            border-radius: 12px;
            font-size: 15px;
            font-family: inherit;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
            background: #fff;
        }

        .grupo-form input:focus, .grupo-form select:focus, .grupo-form textarea:focus {
            outline: none;
            border-color: #f48fb1;
            box-shadow: 0 0 0 4px rgba(244, 143, 177, 0.15);
        }

        .btn-enviar {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #d16074 0%, #e87a90 100%);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 17px;
            cursor: pointer;
            transition: all 0.3s ease;
            letter-spacing: 1px;
        }

        .btn-enviar:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(209, 96, 116, 0.35);
        }

        /* Información de contacto y entrega */
        .info-caja {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 35px;
            text-align: center;
            box-shadow: 0 6px 25px rgba(209, 96, 116, 0.06);
        }

        .info-caja p {
            margin-bottom: 15px;
            color: #5a4a4a;
            font-size: 16px;
        }

        .info-caja a {
            color: #d16074;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .info-caja a:hover {
            color: #b84a60;
        }

        /* Pie de página */
        footer {
            position: relative;
            z-index: 5;
            background-color: rgba(255, 255, 255, 0.85);
            text-align: center;
            padding: 40px 20px;
            margin-top: 30px;
            border-top: 1px solid #f8d7dd;
        }

        footer p {
            color: #7a6a6a;
            font-size: 14px;
        }

        /* Adaptación a móviles */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 15px;
                padding: 20px;
            }
            .nav-links {
                gap: 18px;
                flex-wrap: wrap;
                justify-content: center;
            }
            .hero h1 {
                font-size: 40px;
            }
            section {
                padding: 50px 20px;
            }
            .fondo-logo {
                width: 300px;
                height: 300px;
            }
            .historia-caja, .formulario-caja {
                padding: 30px 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Logo de fondo -->
    <div class="fondo-logo"></div>

    <!-- Navegación -->
    <nav>
        <ul class="nav-links">
            <li><a href="#nosotras">Nosotras</a></li>
            <li><a href="#catalogo">Catálogo</a></li>
        </ul>

        <div class="logo-texto">StrawTime 🍓</div>

        <ul class="nav-links">
            <li><a href="#pedido">Haz tu Pedido</a></li>
            <li><a href="#contacto">Encuéntranos</a></li>
        </ul>
    </nav>

    <!-- Sección Principal -->
    <section class="hero">
        <div class="hero-contenido">
            <h1>StrawTime</h1>
            <p class="eslogan">#vive tu strawtime 🍓</p>
            <p>Donde la fresa, la crema y el cariño se encuentran para convertir cada día en un momento dulce e inolvidable.</p>
            <button class="boton-principal"><a href="#catalogo">Conoce nuestros dulces</a></button>
        </div>
    </section>

    <!-- Nosotras — Historia -->
    <section id="nosotras">
        <h2 class="titulo-seccion">Nuestra historia</h2>
        <p class="subtitulo-seccion">De un día gris, nació algo dulce ✨</p>
        
        <div class="historia-caja">
            <p class="historia-texto">
                Todo comenzó un día cualquiera, uno de esos días grises en los que parece que nada brilla. Estábamos mi amiga Jade, Perla y yo, compartiendo y buscando una forma de transformar esa tarde sin color en algo que nos hiciera sonreír. 🌸<br><br>
                Con ganas de endulzar el momento, preparamos algo sencillo con fresas y crema… y en ese instante mágico, la idea surgió: <strong>¿por qué no llevar esta dulzura a más personas?</strong> 💭<br><br>
                Así nació <strong>StrawTime</strong> — un lugar donde creemos que incluso los días más grises pueden volverse maravillosos con un poco de cariño, unas fresas frescas y el toque especial que solo la amistad y el amor pueden dar. 🍓<br><br>
                <em>Porque cada día merece ser dulce.</em>
            </p>
        </div>
    </section>

    <!-- Catálogo de Productos -->
    <section id="catalogo">
        <h2 class="titulo-seccion">Nuestros dulces favoritos</h2>
        <p class="subtitulo-seccion">Hechos con frescura, amor y mucho cariño 🍓</p>

        <div class="catalogo">
            <!-- Producto 1: Fresa con Crema -->
            <div class="producto">
                <img src="fresa-con-crema.jpg" alt="Fresa con Crema" class="producto-imagen">
                <h3>Fresa con Crema</h3>
                <p>Fresas frescas de temporada con crema suave y el toque justo de dulzura</p>
                <p class="precio">$90</p>
            </div>

            <!-- Producto 2: Fresas con Nutella -->
            <div class="producto">
                <img src="fresas-nutella.jpg" alt="Fresas con Nutella" class="producto-imagen">
                <h3>Fresas con Nutella</h3>
                <p>Fresas jugosas bañadas en crema de avellanas, pura tentación</p>
                <p class="precio">$50</p>
            </div>

            <!-- Producto 3: Flan con Fresa -->
            <div class="producto">
                <img src="flan-fresa.jpg" alt="Flan con Fresa" class="producto-imagen">
                <h3>Flan con Fresa</h3>
                <p>Flan casero cremoso coronado con fresas frescas y mucho amor</p>
                <p class="precio">$150</p>
            </div>
        </div>
    </section>

    <!-- Haz tu Pedido - Formulario -->
    <section id="pedido">
        <h2 class="titulo-seccion">Haz tu pedido</h2>
        <p class="subtitulo-seccion">Regístrate y prepara tu dulce momento ✨</p>
        
        <div class="formulario-caja">
            <form action="#" method="post">
                <div class="grupo-form">
                    <label for="nombre">Tu nombre 🍓</label>
                    <input type="text" id="nombre" name="nombre" placeholder="Escribe tu nombre" required>
                </div>

                <div class="grupo-form">
                    <label for="telefono">Tu teléfono 📱</label>
                    <input type="tel" id="telefono" name="telefono" placeholder="Ej. 829-410-4960" required>
                </div>

                <div class="grupo-form">
                    <label for="producto">¿Qué deseas pedir? 🧁</label>
                    <select id="producto" name="producto" required>
                        <option value="">Selecciona tu dulce favorito</option>
                        <option value="fresa-crema">Fresa con Crema — $90</option>
                        <option value="fresas-nutella">Fresas con Nutella — $50</option>
                        <option value="flan-fresa">Flan con Fresa — $150</option>
                        <option value="variado">Surtido variado</option>
                    </select>
                </div>

                <div class="grupo-form">
                    <label for="cantidad">Cantidad 📦</label>
                    <input type="number" id="cantidad" name="cantidad" min="1" value="1" required>
                </div>

                <div class="grupo-form">
                    <label for="mensaje">Detalles especiales 💌</label>
                    <textarea id="mensaje" name="mensaje" rows="3" placeholder="¿Alguna indicación especial? ¡Dínoslo!"></textarea>
                </div>

                <button type="submit" class="btn-enviar">Enviar Pedido 🍓</button>
            </form>
        </div>
    </section>

    <!-- Encuéntranos - Contacto y Entrega -->
    <section id="contacto">
        <h2 class="titulo-seccion">Encuéntranos</h2>
        <p class="subtitulo-seccion">¡Estamos muy cerca de ti! 💖</p>
        
        <div class="info-caja">
            <p><strong>📱 WhatsApp:</strong><br>
            <a href="https://wa.me/18294104960" target="_blank">829-410-4960</a></p>
            
            <p><strong>📍 Dirección de entrega:</strong><br>
            Carretera Mella, Santo Domingo Este</p>
            
            <p><strong>📸 Síguenos en Instagram:</strong><br>
            <a href="https://instagram.com/strawtime_" target="_blank">@strawtime_</a></p>
        </div>
    </section>

    <!-- Pie de página -->
    <footer>
        <p style="font-size: 24px; font-weight: 600; color: #2c2c2c; margin-bottom: 10px;">StrawTime 🍓</p>
        <p>#vive tu strawtime — Todos los derechos reservados © 2026<br>
        Hecho con 💖 por Jade, Perla y tú</p>
    </footer>
</body>
</html>
