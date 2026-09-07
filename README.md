<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OpenPort | Automatización de Portones</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;700&family=Barlow+Semi+Condensed:wght@400;600&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    <style>
        html { scroll-behavior: smooth; }
        .font-barlow-cond { font-family: 'Barlow Condensed', sans-serif; }
        .font-barlow-semi { font-family: 'Barlow Semi Condensed', sans-serif; }
        .font-space { font-family: 'Space Mono', monospace; }
        .bg-azul-umbral { background-color: #1a2436; } 
        .text-azul-umbral { color: #1a2436; }
        .bg-naranja-apertura { background-color: #f77a1e; } 
        .text-naranja-apertura { color: #f77a1e; }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 font-barlow-semi">

    <!-- Navbar -->
    <nav class="flex justify-between items-center py-4 px-6 bg-azul-umbral text-white sticky top-0 z-50 shadow-md">
        <div class="flex items-center flex-shrink-0 cursor-pointer" onclick="window.scrollTo(0,0)">
            <!-- Isotipo OpenPort Vectorizado -->
            <svg class="w-10 h-10 mr-1.5" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <path d="M50 10 C27.9 10 10 27.9 10 50 C10 72.1 27.9 90 50 90 C68.5 90 84.1 77.4 88.5 60 L73 60 C69 70 60 76 50 76 C35.6 76 24 64.4 24 50 C24 35.6 35.6 24 50 24 C60 24 69 30 73 40 L88.5 40 C84.1 22.6 68.5 10 50 10 Z" fill="#1a2436" stroke="#ffffff" stroke-width="2"/>
                <path d="M73 45 L90 45 L90 78 C90 81 87 83 84 83 L73 83 Z" fill="#f77a1e"/>
                <circle cx="81.5" cy="75" r="3" fill="#ffffff"/>
            </svg>
            <span class="font-barlow-cond text-3xl font-bold tracking-wider pt-1 flex-shrink-0">OPENPORT</span>
        </div>
        
        <!-- Menú Desktop Horizontal -->
        <div class="hidden md:flex space-x-4 whitespace-nowrap text-sm font-space items-center flex-shrink-0">
            <a href="#nosotros" class="hover:text-naranja-apertura transition">NOSOTROS</a>
            <a href="#servicios" class="hover:text-naranja-apertura transition">SERVICIOS</a>
            <a href="#contacto" class="bg-naranja-apertura text-white px-4 py-2 rounded-sm font-bold hover:bg-orange-600 transition shadow-md">COTIZAR</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="bg-azul-umbral text-white py-20 px-6 text-center">
        <h1 class="font-barlow-cond text-6xl md:text-8xl font-bold mb-4 tracking-wide uppercase">Entrá sin bajarte.</h1>
        <p class="font-space text-lg md:text-xl text-gray-300 max-w-2xl mx-auto mb-8">Especialistas en automatización de portones. El motor correcto, instalado con precisión técnica.</p>
        <a href="#contacto" class="inline-block bg-naranja-apertura text-white font-space font-bold text-lg px-8 py-4 rounded-sm hover:bg-orange-600 transition shadow-lg">Solicitar Presupuesto</a>
    </header>

    <!-- Sección Nosotros y Portón Ilustrado -->
    <section id="nosotros" class="py-16 px-6 bg-white text-azul-umbral">
        <div class="max-w-4xl mx-auto text-center">
            
            <!-- Inicio de Ilustración del Portón OpenPort (Diseño Nano Banana) -->
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 500" class="w-full h-auto rounded-xl shadow-lg mb-8">
              <rect width="800" height="500" fill="#8da3b8"/>
              <rect y="450" width="800" height="50" fill="#e0e0e0"/>
              <rect x="50" y="50" width="700" height="400" fill="#2d333b"/>
              <rect x="60" y="60" width="680" height="60" fill="#1e2227"/>
              <rect x="60" y="72" width="680" height="8" fill="#2d333b"/>
              <rect x="60" y="92" width="680" height="8" fill="#2d333b"/>
              <rect x="60" y="130" width="480" height="310" fill="#3a414a"/>
              <rect x="60" y="220" width="480" height="6" fill="#2d333b"/>
              <rect x="60" y="320" width="480" height="6" fill="#2d333b"/>
              <rect x="60" y="265" width="480" height="18" fill="#d1d5db"/>
              <rect x="550" y="130" width="190" height="310" fill="#3a414a"/>
              <rect x="550" y="220" width="190" height="6" fill="#2d333b"/>
              <rect x="550" y="320" width="190" height="6" fill="#2d333b"/>
              <rect x="550" y="265" width="190" height="18" fill="#d1d5db"/>
              <rect x="570" y="235" width="8" height="70" fill="#d1d5db" rx="4"/>
              <circle cx="560" cy="270" r="5" fill="#1e2227"/>
            </svg>
            <!-- Fin de Ilustración -->

            <h2 class="text-3xl font-barlow-cond font-bold mb-2">El Protector, con oficio de Sabio</h2>
            <p class="text-2xl font-barlow-semi text-naranja-apertura mb-4">El vecino que además es eléctrico.</p>
            <p class="font-space text-gray-600">Umbral Técnico. Brindamos una solución técnica y un servicio que responde. Confianza, durabilidad y respuesta inmediata para tu tranquilidad.</p>
        </div>
    </section>

    <!-- Sección Diferenciadores -->
    <section id="servicios" class="py-16 px-6 bg-gray-100">
        <div class="max-w-6xl mx-auto">
            <h2 class="text-4xl font-barlow-cond font-bold text-center text-azul-umbral mb-12">¿Por qué elegir OpenPort?</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-white p-8 rounded-lg shadow-sm border-t-4 border-naranja-apertura text-center">
                    <h3 class="font-barlow-cond text-5xl font-bold text-azul-umbral mb-2">24 h</h3>
                    <p class="font-space text-gray-600">Respuesta técnica garantizada.</p>
                </div>
                <div class="bg-white p-8 rounded-lg shadow-sm border-t-4 border-naranja-apertura text-center">
                    <h3 class="font-barlow-cond text-5xl font-bold text-azul-umbral mb-2">48 h</h3>
                    <p class="font-space text-gray-600">Instalación completa de tu equipo.</p>
                </div>
                <div class="bg-white p-8 rounded-lg shadow-sm border-t-4 border-naranja-apertura text-center">
                    <h3 class="font-barlow-cond text-5xl font-bold text-azul-umbral mb-2">2 años</h3>
                    <p class="font-space text-gray-600">Garantía escrita en todos los motores.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Banner Cotización -->
    <section class="bg-naranja-apertura py-12 px-6 text-center text-white">
        <h2 class="font-barlow-cond text-5xl font-bold mb-4 uppercase">¿Cuánto sale automatizar tu portón?</h2>
        <p class="font-space mb-6">Contactanos hoy mismo y recibí tu presupuesto sin cargo.</p>
    </section>

    <!-- Contacto e Instagram -->
    <section id="contacto" class="py-16 px-6 bg-white">
        <div class="max-w-4xl mx-auto flex flex-col md:flex-row gap-10">
            <div class="w-full md:w-1/2">
                <h3 class="font-barlow-cond text-4xl font-bold text-azul-umbral mb-4">Contactanos</h3>
                <p class="font-space text-gray-600 mb-6">Completa los datos de tu portón o envianos un mensaje directo. Te asesoramos sobre la mejor opción.</p>
                
                <div class="mb-4">
                    <p class="font-bold text-azul-umbral font-barlow-semi">WhatsApp:</p>
                    <p class="font-space text-gray-600">+54 9 261 000-0000</p>
                </div>
                <div class="mb-4">
                    <p class="font-bold text-azul-umbral font-barlow-semi">Instagram:</p>
                    <a href="https://instagram.com/openport.mza" target="_blank" class="font-space text-naranja-apertura hover:underline">@openport.mza</a>
                </div>
                <div>
                    <p class="font-bold text-azul-umbral font-barlow-semi">Ubicación:</p>
                    <p class="font-space text-gray-600">Mendoza, Argentina</p>
                </div>
            </div>
            
            <div class="w-full md:w-1/2 bg-gray-50 p-6 rounded-lg shadow-sm border border-gray-200">
                <form action="#" method="POST" class="flex flex-col space-y-4">
                    <input type="text" placeholder="Tu Nombre" class="p-3 border border-gray-300 rounded focus:outline-none focus:border-naranja-apertura font-space text-sm">
                    <input type="tel" placeholder="Tu Teléfono" class="p-3 border border-gray-300 rounded focus:outline-none focus:border-naranja-apertura font-space text-sm">
                    <select class="p-3 border border-gray-300 rounded focus:outline-none focus:border-naranja-apertura font-space text-sm text-gray-600">
                        <option value="" disabled selected>Tipo de Portón...</option>
                        <option value="corredizo">Corredizo</option>
                        <option value="levadizo">Levadizo</option>
                        <option value="pivotante">Pivotante</option>
                        <option value="no_se">No estoy seguro</option>
                    </select>
                    <button type="submit" class="bg-azul-umbral text-white font-bold font-space py-3 rounded hover:bg-gray-800 transition">ENVIAR CONSULTA</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-azul-umbral text-white py-8 px-6 text-center border-t border-gray-700">
        <div class="flex justify-center items-center mb-4">
            <!-- Isotipo Footer -->
            <svg class="w-8 h-8 mr-2" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <path d="M50 10 C27.9 10 10 27.9 10 50 C10 72.1 27.9 90 50 90 C68.5 90 84.1 77.4 88.5 60 L73 60 C69 70 60 76 50 76 C35.6 76 24 64.4 24 50 C24 35.6 35.6 24 50 24 C60 24 69 30 73 40 L88.5 40 C84.1 22.6 68.5 10 50 10 Z" fill="#1a2436" stroke="#ffffff" stroke-width="2"/>
                <path d="M73 45 L90 45 L90 78 C90 81 87 83 84 83 L73 83 Z" fill="#f77a1e"/>
                <circle cx="81.5" cy="75" r="3" fill="#ffffff"/>
            </svg>
            <span class="font-barlow-cond text-2xl font-bold tracking-wider">OPENPORT</span>
        </div>
        <p class="font-space text-sm text-gray-400">&copy; 2026 OpenPort. Todos los derechos reservados. Mendoza, Argentina.</p>
    </footer>

    <!-- Botón Flotante de WhatsApp -->
    <a href="https://wa.me/5492610000000?text=Hola%20OpenPort!%20Me%20gustar%C3%ADa%20hacer%20una%20consulta." 
       target="_blank" 
       class="fixed bottom-6 right-6 bg-[#25D366] text-white w-14 h-14 rounded-full flex items-center justify-center shadow-2xl hover:bg-[#1ebd57] transition-all hover:scale-110 z-50 animate-bounce"
       aria-label="Contactar por WhatsApp">
        <svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12.031 6.172c-3.181 0-5.767 2.586-5.768 5.766-.001 1.298.38 2.27 1.019 3.287l-.582 2.128 2.182-.573c.978.58 1.911.928 3.145.929 3.178 0 5.767-2.587 5.768-5.766.001-3.187-2.575-5.77-5.764-5.771zm3.392 8.244c-.144.405-.837.774-1.17.824-.299.045-.677.063-1.092-.069-.252-.08-.575-.187-.988-.365-1.739-.751-2.874-2.502-2.961-2.617-.087-.116-.708-.94-.708-1.793s.448-1.273.607-1.446c.159-.173.346-.217.462-.217l.332.006c.106.005.249-.04.39.298.144.347.491 1.2.534 1.287.043.087.072.188.014.304-.058.116-.087.188-.173.289l-.26.304c-.087.086-.177.18-.076.354.101.174.449.741.964 1.201.662.591 1.221.774 1.394.86s.274.072.376-.043c.101-.116.433-.506.549-.68.116-.173.231-.145.39-.087s1.011.477 1.184.564c.173.087.289.129.332.202.043.073.043.423-.101.827z"/>
        </svg>
    </a>

</body>
</html>
