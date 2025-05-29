<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Consultoría Ambiental y Social - Especialistas en Normativa Peruana</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        /* Header */
        .header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #2c5282;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            cursor: pointer;
        }

        .nav-links a:hover {
            color: #2c5282;
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Sections */
        .section {
            min-height: 100vh;
            padding: 100px 0 50px;
            display: none;
        }

        .section.active {
            display: block;
        }

        /* Inicio Section */
        .hero {
            background: linear-gradient(135deg, rgba(44, 82, 130, 0.9), rgba(118, 75, 162, 0.9)), 
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23228B22" width="1200" height="600"/><circle fill="%2332CD32" cx="200" cy="150" r="50" opacity="0.3"/><circle fill="%2390EE90" cx="800" cy="400" r="80" opacity="0.2"/><rect fill="%23006400" x="0" y="500" width="1200" height="100" opacity="0.4"/></svg>');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            display: flex;
            align-items: center;
            min-height: 100vh;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: fadeInUp 1s ease-out;
        }

        .hero-content p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .service-card i {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #90EE90;
        }

        .benefits {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .benefit-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 1.5rem;
            border-radius: 10px;
            border-left: 4px solid #90EE90;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #32CD32, #228B22);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            text-decoration: none;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(50, 205, 50, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(50, 205, 50, 0.4);
        }

        /* Catalog Section */
        .catalog {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            color: #333;
        }

        .catalog h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c5282;
        }

        .services-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .service-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .service-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .service-image {
            height: 200px;
            background: linear-gradient(45deg, #32CD32, #228B22);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .service-image i {
            font-size: 4rem;
            color: white;
        }

        .service-content {
            padding: 1.5rem;
        }

        .service-content h3 {
            color: #2c5282;
            margin-bottom: 1rem;
        }

        .expand-btn {
            background: #2c5282;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .expand-btn:hover {
            background: #1a365d;
        }

        .service-details {
            display: none;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px solid #eee;
            color: #666;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, #2c5282, #1a365d);
            color: white;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: start;
        }

        .contact-form {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            font-size: 1rem;
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .contact-info {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .contact-item i {
            font-size: 1.5rem;
            margin-right: 1rem;
            color: #90EE90;
            width: 30px;
        }

        .quick-contacts {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .quick-contact-btn {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            background: #25D366;
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            text-decoration: none;
            transition: transform 0.3s ease;
        }

        .quick-contact-btn:hover {
            transform: translateY(-2px);
        }

        .quick-contact-btn.email {
            background: #0073e6;
        }

        /* About Section */
        .about {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            color: #333;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-content {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .about-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .feature-card {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
        }

        .feature-card i {
            font-size: 2.5rem;
            color: #32CD32;
            margin-bottom: 1rem;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .services-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-grid,
            .about-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }
            
            .nav-links {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: white;
                flex-direction: column;
                padding: 1rem;
                box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            }
            
            .nav-links.show {
                display: flex;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <nav class="nav">
            <a href="#" class="logo">
                <i class="fas fa-leaf"></i> EcoConsultoría
            </a>
            <ul class="nav-links" id="navLinks">
                <li><a onclick="showSection('inicio')">Inicio</a></li>
                <li><a onclick="showSection('catalogo')">Catálogo</a></li>
                <li><a onclick="showSection('contacto')">Contacto</a></li>
                <li><a onclick="showSection('nosotros')">Nosotros</a></li>
            </ul>
            <button class="mobile-menu-btn" onclick="toggleMobileMenu()">
                <i class="fas fa-bars"></i>
            </button>
        </nav>
    </header>

    <!-- Inicio Section -->
    <section id="inicio" class="section active">
        <div class="hero">
            <div class="container">
                <div class="hero-content">
                    <h1>Consultoría Ambiental y Social</h1>
                    <p>Especialistas en normativa ambiental peruana - Comprometidos con la sostenibilidad y el desarrollo territorial</p>
                    
                    <div class="services-grid">
                        <div class="service-card">
                            <i class="fas fa-leaf"></i>
                            <h3>Ambiental</h3>
                            <p>Estudios, monitoreo y gestión ambiental</p>
                        </div>
                        <div class="service-card">
                            <i class="fas fa-users"></i>
                            <h3>Social</h3>
                            <p>Gestión comunitaria y permisos sociales</p>
                        </div>
                        <div class="service-card">
                            <i class="fas fa-monument"></i>
                            <h3>Arqueología</h3>
                            <p>Gestión de permisos arqueológicos</p>
                        </div>
                        <div class="service-card">
                            <i class="fas fa-hard-hat"></i>
                            <h3>SST</h3>
                            <p>Seguridad y salud en el trabajo</p>
                        </div>
                    </div>

                    <div class="benefits">
                        <div class="benefit-item">
                            <h4><i class="fas fa-user-graduate"></i> Personal Especializado</h4>
                            <p>Equipo multidisciplinario con amplia experiencia</p>
                        </div>
                        <div class="benefit-item">
                            <h4><i class="fas fa-gavel"></i> Experiencia Normativa</h4>
                            <p>Conocimiento profundo de la legislación ambiental peruana</p>
                        </div>
                        <div class="benefit-item">
                            <h4><i class="fas fa-map-marked-alt"></i> Enfoque Territorial</h4>
                            <p>Trabajo directo con comunidades locales</p>
                        </div>
                    </div>

                    <button class="cta-button" onclick="showSection('contacto')">
                        Contáctanos para una Asesoría Gratuita
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Catálogo Section -->
    <section id="catalogo" class="section catalog">
        <div class="container">
            <h2>Nuestros Servicios</h2>
            <div class="services-list">
                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-eye"></i>
                    </div>
                    <div class="service-content">
                        <h3>Supervisión Ambiental en Campo</h3>
                        <p>Supervisión especializada conforme a la legislación ambiental peruana, asegurando el cumplimiento normativo.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Servicio integral de supervisión ambiental que incluye monitoreo de parámetros ambientales, verificación de cumplimiento de medidas de manejo ambiental, y elaboración de informes técnicos especializados.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="service-content">
                        <h3>Elaboración de Línea de Base Socioambiental</h3>
                        <p>Estudios técnicos para establecer condiciones iniciales del entorno socioambiental.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Desarrollo de líneas base integrales que incluyen caracterización ambiental, social y económica del área de influencia, cumpliendo con estándares técnicos y normativos vigentes.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-clipboard-check"></i>
                    </div>
                    <div class="service-content">
                        <h3>Subsanación de Observaciones Ambientales</h3>
                        <p>Atención especializada de observaciones formuladas por autoridades ambientales.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Análisis técnico y legal de observaciones ambientales, elaboración de respuestas fundamentadas y acompañamiento en procesos de subsanación ante SENACE y otras autoridades.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-map"></i>
                    </div>
                    <div class="service-content">
                        <h3>Elaboración de Mapas Temáticos Socioambientales</h3>
                        <p>Cartografía especializada para proyectos ambientales y sociales.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Desarrollo de mapas temáticos con sistemas de información geográfica (SIG), incluyendo mapas de zonificación, uso de suelos, áreas de influencia y componentes socioambientales.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-monument"></i>
                    </div>
                    <div class="service-content">
                        <h3>Gestión de Permisos Arqueológicos</h3>
                        <p>Tramitación y gestión de permisos ante el Ministerio de Cultura.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Gestión integral de certificados de inexistencia de restos arqueológicos (CIRA), planes de monitoreo arqueológico y proyectos de evaluación arqueológica ante MINCUL.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-file-alt"></i>
                    </div>
                    <div class="service-content">
                        <h3>Elaboración de Estudios Ambientales</h3>
                        <p>Estudios de impacto ambiental y declaraciones de impacto ambiental.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Elaboración de EIA-d, EIA-sd, DIA y otros instrumentos de gestión ambiental, cumpliendo con los términos de referencia y normativa sectorial vigente.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-handshake"></i>
                    </div>
                    <div class="service-content">
                        <h3>Gestión de Permisos Sociales</h3>
                        <p>Facilitación de procesos de consulta y participación ciudadana.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Gestión de procesos de participación ciudadana, talleres informativos, consultas previas y negociación de acuerdos con comunidades locales y stakeholders.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-clipboard-list"></i>
                    </div>
                    <div class="service-content">
                        <h3>Elaboración de Informes de Cumplimiento</h3>
                        <p>Informes técnicos de seguimiento y cumplimiento ambiental.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Elaboración de informes de cumplimiento de medidas ambientales, reportes de monitoreo, informes anuales consolidados y documentos técnicos para autoridades competentes.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-chalkboard-teacher"></i>
                    </div>
                    <div class="service-content">
                        <h3>Capacitación Ambiental</h3>
                        <p>Programas de capacitación en gestión ambiental y normativa.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Programas de capacitación dirigidos a personal técnico, trabajadores y comunidades en temas de gestión ambiental, manejo de residuos, y cumplimiento normativo.</p>
                        </div>
                    </div>
                </div>

                <div class="service-item">
                    <div class="service-image">
                        <i class="fas fa-flask"></i>
                    </div>
                    <div class="service-content">
                        <h3>Monitoreo Ambiental</h3>
                        <p>Monitoreo de aire, agua, ruido y suelo conforme a ECA y LMP peruanos.</p>
                        <button class="expand-btn" onclick="toggleDetails(this)">Ver más</button>
                        <div class="service-details">
                            <p>Programas de monitoreo ambiental integral, incluyendo calidad de aire, agua superficial y subterránea, niveles de ruido y calidad de suelos, con laboratorios acreditados ante INACAL.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contacto Section -->
    <section id="contacto" class="section contact">
        <div class="container">
            <h2 style="text-align: center; margin-bottom: 3rem; color: white;">Contáctanos</h2>
            <div class="contact-grid">
                <div class="contact-form">
                    <h3 style="margin-bottom: 1.5rem;">Solicita una Cotización</h3>
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="nombre">Nombre Completo</label>
                            <input type="text" id="nombre" name="nombre" required>
                        </div>
                        <div class="form-group">
                            <label for="correo">Correo Electrónico</label>
                            <input type="email" id="correo" name="correo" required>
                        </div>
                        <div class="form-group">
                            <label for="telefono">Teléfono</label>
                            <input type="tel" id="telefono" name="telefono" required>
                        </div>
                        <div class="form-group">
                            <label for="servicio">Servicio de Interés</label>
                            <select id="servicio" name="servicio" required>
                                <option value="">Seleccione un servicio</option>
                                <option value="supervision">Supervisión Ambiental en Campo</option>
                                <option value="linea-base">Elaboración de Línea de Base Socioambiental</option>
                                <option value="subsanacion">Subsanación de Observaciones Ambientales</option>
                                <option value="mapas">Elaboración de Mapas Temáticos Socioambientales</option>
                                <option value="arqueologia">Gestión de Permisos Arqueológicos</option>
                                <option value="estudios">Elaboración de Estudios Ambientales</option>
                                <option value="permisos-sociales">Gestión de Permisos Sociales</option>
                                <option value="informes">Elaboración de Informes de Cumplimiento</option>
                                <option value="capacitacion">Capacitación Ambiental</option>
                                <option value="monitoreo">Monitoreo Ambiental</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="mensaje">Mensaje</label>
                            <textarea id="mensaje" name="mensaje" placeholder="Describa brevemente su proyecto o consulta"></textarea>
                        </div>
                        <button type="submit" class="cta-button" style="width: 100%;">Enviar Consulta</button>
                    </form>
                </div>

                <div class="contact-info">
                    <h3 style="margin-bottom: 1.5rem;">Información de Contacto</h3>
                    
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <div>
                            <strong>Teléfono:</strong><br>
                            +51 956 298 271
                        </div>
                    </div>

                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div>
                            <strong>Correo Electrónico:</strong><br>
                            walas8712@gmail.com
                        </div>
                    </div>

                    <div class="contact-item">
                        <i class="fas fa-clock"></i>
                        <div>
                            <strong>Horario de Atención:</strong><br>
                            Lunes a Viernes: 8:00 AM - 6:00 PM<br>
                            Sábados: 9:00 AM - 1:00 PM
                        </div>
                    </div>

                    <div class="contact-item">
                        <i class="fas fa-credit-card"></i>
                        <div>
                            <strong>Formas de Pago:</strong><br>
                            Transferencias bancarias, Yape y otros métodos disponibles
                        </div>
                    </div>

                    <div class="quick-contacts">
                        <a href="https://wa.me/51956298271" class="quick-contact-btn" target="_blank">
                            <i class="fab fa-whatsapp"></i>
                            WhatsApp
                        </a>
                        <a href="mailto:walas8712@gmail.com" class="quick-contact-btn email">
                            <i class="fas fa-envelope"></i>
                            Email
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Nosotros Section -->
    <section id="nosotros" class="section about">
        <div class="container">
            <h2 style="text-align: center; margin-bottom: 3rem; color: #2c5282;">Sobre Nosotros</h2>
            
            <div class="about-grid">
                <div class="about-content">
                    <h3 style="color: #2c5282; margin-bottom: 1rem;">¿Quiénes Somos?</h3>
                    <p style="margin-bottom: 1rem;">Somos una empresa especializada en consultoría ambiental y social, comprometida con el desarrollo sostenible y el cumplimiento de la normativa ambiental peruana. Nuestro equipo multidisciplinario cuenta con amplia experiencia en el sector ambiental, social y arqueológico.</p>
                    
                    <h4 style="color: #32CD32; margin-bottom: 0.5rem; margin-top: 1.5rem;">Misión</h4>
                    <p style="margin-bottom: 1rem;">Brindar servicios de consultoría ambiental y social de excelencia, contribuyendo al desarrollo sostenible de los proyectos de nuestros clientes mediante el cumplimiento riguroso de la normativa peruana y el respeto por las comunidades locales.</p>
                    
                    <h4 style="color: #32CD32; margin-bottom: 0.5rem;">Visión</h4>
                    <p style="margin-bottom: 1rem;">Ser reconocidos como la empresa líder en consultoría ambiental y social en el Perú, destacando por nuestra calidad técnica, ética profesional y compromiso con la sostenibilidad.</p>
                    
                    <h4 style="color: #32CD32; margin-bottom: 0.5rem;">Valores</h4>
                    <ul style="margin-left: 1rem;">
                        <li>Excelencia técnica y profesional</li>
                        <li>Integridad y transparencia</li>
                        <li>Compromiso con la sostenibilidad</li>
                        <li>Respeto por las comunidades locales</li>
                        <li>Innovación y mejora continua</li>
                    </ul>
                </div>
                
                <div class="about-content">
                    <h3 style="color: #2c5282; margin-bottom: 1rem;">Nuestro Enfoque</h3>
                    <p style="margin-bottom: 1rem;">Desarrollamos nuestro trabajo con un enfoque integral que combina:</p>
                    
                    <div style="margin-bottom: 1.5rem;">
                        <h4 style="color: #32CD32; margin-bottom: 0.5rem;"><i class="fas fa-gavel" style="margin-right: 0.5rem;"></i>Cumplimiento Normativo</h4>
                        <p>Conocimiento profundo y actualizado de la legislación ambiental peruana, asegurando el cumplimiento de todas las disposiciones legales vigentes.</p>
                    </div>
                    
                    <div style="margin-bottom: 1.5rem;">
                        <h4 style="color: #32CD32; margin-bottom: 0.5rem;"><i class="fas fa-leaf" style="margin-right: 0.5rem;"></i>Sostenibilidad</h4>
                        <p>Promovemos prácticas ambientalmente responsables que contribuyan al desarrollo sostenible y la conservación de los recursos naturales.</p>
                    </div>
                    
                    <div style="margin-bottom: 1.5rem;">
                        <h4 style="color: #32CD32; margin-bottom: 0.5rem;"><i class="fas fa-users" style="margin-right: 0.5rem;"></i>Desarrollo Local</h4>
                        <p>Trabajamos de la mano con las comunidades locales, promoviendo su participación activa y el respeto por sus derechos y tradiciones.</p>
                    </div>
                </div>
            </div>

            <div class="about-features">
                <div class="feature-card">
                    <i class="fas fa-user-graduate"></i>
                    <h4 style="color: #2c5282;">Equipo Especializado</h4>
                    <p>Profesionales con formación en ingeniería ambiental, arqueología, ciencias sociales, SST y disciplinas afines.</p>
                </div>
                
                <div class="feature-card">
                    <i class="fas fa-certificate"></i>
                    <h4 style="color: #2c5282;">Certificaciones</h4>
                    <p>Registro de consultoras ambientales ante SENACE y certificaciones en sistemas de gestión ambiental y SST.</p>
                </div>
                
                <div class="feature-card">
                    <i class="fas fa-industry"></i>
                    <h4 style="color: #2c5282;">Sectores Atendidos</h4>
                    <p>Experiencia en minería, energía, construcción, industria, agricultura y proyectos de infraestructura.</p>
                </div>
                
                <div class="feature-card">
                    <i class="fas fa-handshake"></i>
                    <h4 style="color: #2c5282;">Alianzas Estratégicas</h4>
                    <p>Colaboraciones con universidades, organizaciones técnicas y entidades especializadas del sector.</p>
                </div>
            </div>
            
            <div class="about-content" style="margin-top: 3rem; text-align: center;">
                <h3 style="color: #2c5282; margin-bottom: 1rem;">¿Por Qué Elegirnos?</h3>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; margin-top: 2rem;">
                    <div style="background: white; padding: 1.5rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
                        <h4 style="color: #32CD32; margin-bottom: 0.5rem;">Experiencia Comprobada</h4>
                        <p>Años de experiencia exitosa en proyectos de diversa complejidad y escala.</p>
                    </div>
                    <div style="background: white; padding: 1.5rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
                        <h4 style="color: #32CD32; margin-bottom: 0.5rem;">Atención Personalizada</h4>
                        <p>Cada proyecto recibe atención especializada y soluciones adaptadas a sus necesidades específicas.</p>
                    </div>
                    <div style="background: white; padding: 1.5rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
                        <h4 style="color: #32CD32; margin-bottom: 0.5rem;">Entrega Oportuna</h4>
                        <p>Comprometidos con el cumplimiento de plazos y la entrega de resultados de calidad.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Navigation
        function showSection(sectionId) {
            // Hide all sections
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => section.classList.remove('active'));
            
            // Show selected section
            document.getElementById(sectionId).classList.add('active');
            
            // Update URL hash
            window.location.hash = sectionId;
            
            // Close mobile menu if open
            document.getElementById('navLinks').classList.remove('show');
        }

        // Mobile menu toggle
        function toggleMobileMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('show');
        }

        // Service details toggle
        function toggleDetails(button) {
            const details = button.parentElement.querySelector('.service-details');
            if (details.style.display === 'block') {
                details.style.display = 'none';
                button.textContent = 'Ver más';
            } else {
                details.style.display = 'block';
                button.textContent = 'Ver menos';
            }
        }

        // Contact form handling
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = new FormData(this);
            const data = Object.fromEntries(formData);
            
            // Create email content
            const subject = encodeURIComponent('Consulta desde sitio web - ' + data.servicio);
            const body = encodeURIComponent(`
Nombre: ${data.nombre}
Correo: ${data.correo}
Teléfono: ${data.telefono}
Servicio de interés: ${data.servicio}
Mensaje: ${data.mensaje}
            `);
            
            // Open email client
            window.location.href = `mailto:walas8712@gmail.com?subject=${subject}&body=${body}`;
            
            // Show confirmation
            alert('Se abrirá su cliente de correo para enviar la consulta. ¡Gracias por contactarnos!');
            
            // Reset form
            this.reset();
        });

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            // Check URL hash on page load
            const hash = window.location.hash.substring(1);
            if (hash && document.getElementById(hash)) {
                showSection(hash);
            }
            
            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth'
                        });
                    }
                });
            });
        });

        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.querySelector('.header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.backdropFilter = 'blur(15px)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.backdropFilter = 'blur(10px)';
            }
        });
    </script>
</body>
</html># pagina_web_inemac_02
