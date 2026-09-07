<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OpenPort | Automatización de Portones</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            blue: '#1E3A8A',
                            orange: '#F97316',
                            dark: '#0F172A',
                            gray: '#475569'
                        }
                    },
                    fontFamily: {
                        sans: ['"Barlow Semi Condensed"', 'sans-serif'],
                        condensed: ['"Barlow Condensed"', 'sans-serif'],
                        mono: ['"Space Mono"', 'monospace'],
                    }
                }
            }
        }
    </script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700&family=Barlow+Semi+Condensed:wght@400;600;700&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Barlow Semi Condensed', sans-serif; }
        /* Corrección de la imagen de fondo: URL estable y propiedades separadas */
        .hero-gradient {
            background-color: #1E3A8A; 
            background-image: linear-gradient(135deg, rgba(15, 23, 42, 0.95) 0%, rgba(30, 58, 138, 0.85) 100%), url('https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }
    </style>
</head>
<body class="bg-gray-50 text-brand-dark antialiased selection:bg-brand-orange selection:text-white">

    <header class="fixed w-full top-0 z-50 bg-white/95 backdrop-blur-md shadow-sm transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20 gap-4">
                
                <!-- Logo OpenPort con el nuevo Isotipo 'O' -->
                <div class="flex-shrink-0 flex items-center cursor-pointer z-50">
                    <div id="isotipo-container" class="mr-2 flex items-center justify-center">
                        <svg class="h-10 w-10 md:h-11 md:w-11" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                            <path d="M50 10 C27.9 10 10 27.9 10 50 C10 72.1 27.9 90 50 90 C68.5 90 84.1 77.4 88.5 60 L73 60 C69 70 60 76 50 76 C35.6 76 24 64.4 24 50 C24 35.6 35.6 24 50 24 C60 24 69 30 73 40 L88.5 40 C84.1 22.6 68.5 10 50 10 Z" fill="#1E3A8A" stroke="#ffffff" stroke-width="2"/>
                            <path d="M73 45 L90 45 L90 78 C90 81 87 83 84 83 L73 83 Z" fill="#F97316"/>
                            <circle cx="81.5" cy="75" r="3" fill="#ffffff"/>
                        </svg>
                    </div>
                    <span class="font-condensed font-bold text-3xl md:text-4xl tracking-tight text-brand-dark">OPENPORT</span>
                </div>
                
                <!-- Menú Desktop - Corregido para evitar superposición -->
                <div class="hidden xl:flex flex-1 justify-end items-center pr-6">
                    <nav class="flex space-x-6 items-center">
                        <a href="#inicio" class="text-brand-gray hover:text-brand-orange font-semibold font-condensed text-base uppercase tracking-wider transition-colors whitespace-nowrap">Inicio</a>
                        <a href="#servicios" class="text-brand-gray hover:text-brand-orange font-semibold font-condensed text-base uppercase tracking-wider transition-colors whitespace-nowrap">Servicios</a>
                        <a href="#nosotros" class="text-brand-gray hover:text-brand-orange font-semibold font-condensed text-base uppercase tracking-wider transition-colors whitespace-nowrap">Nosotros</a>
                        <a href="#contacto" class="text-brand-gray hover:text-brand-orange font-semibold font-condensed text-base uppercase tracking-wider transition-colors whitespace-nowrap">Contacto</a>
                    </nav>
                </div>
                
                <!-- Botón de acción principal -->
                <div class="hidden md:flex flex-shrink-0">
                    <a href="#contacto" class="bg-brand-orange hover:bg-orange-600 text-white px-5 py-2.5 rounded-sm font-mono text-sm font-bold transition-all shadow-md hover:shadow-lg transform hover:-translate-y-0.5 tracking-wider whitespace-nowrap">
                        COTIZAR PORTÓN
                    </a>
                </div>
                
                <!-- Botón de menú móvil -->
                <div class="xl:hidden flex items-center flex-shrink-0 ml-4">
                    <button id="mobile-menu-btn" class="text-brand-dark hover:text-brand-orange focus:outline-none p-2">
                        <svg id="menu-icon-bars" class="w-7 h-7 block" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
                        <svg id="menu-icon-close" class="w-7 h-7 hidden" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                    </button>
                </div>
            </div>
        </div>
        
        <div id="mobile-menu" class="hidden xl:hidden bg-white border-t border-gray-100 absolute w-full shadow-lg">
            <div class="px-4 pt-2 pb-6 space-y-1">
                <a href="#inicio" class="block px-3 py-3 font-condensed text-lg font-bold text-brand-blue hover:text-brand-orange hover:bg-gray-50 rounded-sm uppercase">Inicio</a>
                <a href="#servicios" class="block px-3 py-3 font-condensed text-lg font-bold text-brand-blue hover:text-brand-orange hover:bg-gray-50 rounded-sm uppercase">Servicios</a>
                <a href="#nosotros" class="block px-3 py-3 font-condensed text-lg font-bold text-brand-blue hover:text-brand-orange hover:bg-gray-50 rounded-sm uppercase">Nosotros</a>
                <a href="#contacto" class="block px-3 py-3 font-condensed text-lg font-bold text-brand-blue hover:text-brand-orange hover:bg-gray-50 rounded-sm uppercase">Contacto</a>
            </div>
        </div>
    </header>

    <main>
        <section id="inicio" class="hero-gradient relative pt-32 pb-20 lg:pt-48 lg:pb-32 flex items-center min-h-screen">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center w-full">
                <span class="font-mono inline-block py-1 px-3 bg-brand-blue/40 text-blue-100 border border-brand-blue/60 font-bold text-xs mb-6 uppercase tracking-widest rounded-sm">
                    Especialistas en automatización · Mendoza
                </span>
                <h1 class="font-condensed text-5xl sm:text-6xl lg:text-8xl font-bold text-white tracking-normal mb-6 uppercase shadow-sm">
                    Entrá sin <span class="text-brand-orange">bajarte.</span>
                </h1>
                <p class="mt-4 text-xl sm:text-2xl text-gray-200 max-w-3xl mx-auto font-medium mb-10">
                    El motor correcto para tu portón. Combinamos la precisión técnica con la confianza del vecino de toda la vida.
                </p>
                <div class="flex flex-col sm:flex-row justify-center gap-4">
                    <a href="#contacto" class="bg-brand-orange hover:bg-orange-600 text-white px-8 py-4 rounded-sm font-mono font-bold text-sm transition-all shadow-lg hover:shadow-orange-500/30 flex items-center justify-center uppercase tracking-wider">
                        ¿Cuánto sale automatizar? 
                        <svg class="w-5 h-5 ml-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                    </a>
                    <a href="#servicios" class="bg-white/10 hover:bg-white/20 backdrop-blur-sm text-white border border-white/30 px-8 py-4 rounded-sm font-mono font-bold text-sm transition-all flex items-center justify-center uppercase tracking-wider">
                        Ver servicios 
                        <svg class="w-5 h-5 ml-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path></svg>
                    </a>
                </div>
            </div>
        </section>

        <section id="servicios" class="py-24 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="font-condensed text-4xl md:text-5xl font-bold text-brand-blue mb-4 uppercase tracking-wide">Umbral Técnico</h2>
                    <div class="w-24 h-1 bg-brand-orange mx-auto mb-6"></div>
                    <p class="text-lg text-brand-gray max-w-2xl mx-auto font-medium">Soluciones integrales de acceso. Somos el protector de tu hogar con el oficio de un sabio.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
                    <div class="bg-gray-50 rounded-lg p-8 border-t-4 border-brand-orange shadow-sm hover:shadow-xl transition-all duration-300 group">
                        <div class="w-14 h-14 bg-brand-blue/10 rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform text-brand-blue">
                            <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"></path></svg>
                        </div>
                        <h3 class="font-condensed text-2xl font-bold text-brand-dark mb-3 uppercase tracking-wide">Automatización</h3>
                        <p class="text-brand-gray leading-relaxed mb-4">Instalación del motor correcto para tu portón corredizo, levadizo o pivotante.</p>
                        <span class="font-mono text-sm text-brand-orange font-bold uppercase tracking-wider">Instalación en 48 h</span>
                    </div>

                    <div class="bg-gray-50 rounded-lg p-8 border-t-4 border-brand-blue shadow-sm hover:shadow-xl transition-all duration-300 group">
                        <div class="w-14 h-14 bg-brand-blue/10 rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform text-brand-blue">
                            <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        </div>
                        <h3 class="font-condensed text-2xl font-bold text-brand-dark mb-3 uppercase tracking-wide">Servicio Técnico</h3>
                        <p class="text-brand-gray leading-relaxed mb-4">Reparación, mantenimiento preventivo y configuración de controles remotos y placas.</p>
                        <span class="font-mono text-sm text-brand-blue font-bold uppercase tracking-wider">Soporte técnico 24 h</span>
                    </div>

                    <div class="bg-gray-50 rounded-lg p-8 border-t-4 border-brand-orange shadow-sm hover:shadow-xl transition-all duration-300 group">
                        <div class="w-14 h-14 bg-brand-blue/10 rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform text-brand-blue">
                            <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
                        </div>
                        <h3 class="font-condensed text-2xl font-bold text-brand-dark mb-3 uppercase tracking-wide">Garantía y Calidad</h3>
                        <p class="text-brand-gray leading-relaxed mb-4">Trabajamos con las mejores marcas del mercado para asegurar la durabilidad de tu acceso.</p>
                        <span class="font-mono text-sm text-brand-orange font-bold uppercase tracking-wider">Garantía de 2 años</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="nosotros" class="py-24 bg-brand-dark text-white overflow-hidden">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex flex-col lg:flex-row items-center gap-16">
                    <div class="lg:w-1/2 relative w-full">
                        <!-- ILUSTRACIÓN TÉCNICA DEL PORTÓN INTEGRADA DIRECTAMENTE -->
                        <div class="relative w-full rounded-sm overflow-hidden shadow-2xl border-l-4 border-brand-orange bg-gray-900">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 500" class="w-full h-auto opacity-90 block">
                                <!-- Pared de fondo y piso -->
                                <rect width="800" height="500" fill="#8da3b8"/>
                                <rect y="450" width="800" height="50" fill="#e0e0e0"/>
                                <!-- Marco principal del portón -->
                                <rect x="50" y="50" width="700" height="400" fill="#2d333b"/>
                                <!-- Reja superior (ventilación) -->
                                <rect x="60" y="60" width="680" height="60" fill="#1e2227"/>
                                <rect x="60" y="72" width="680" height="8" fill="#2d333b"/>
                                <rect x="60" y="92" width="680" height="8" fill="#2d333b"/>
                                <!-- Hoja principal del portón corredizo (Izquierda) -->
                                <rect x="60" y="130" width="480" height="310" fill="#3a414a"/>
                                <rect x="60" y="220" width="480" height="6" fill="#2d333b"/>
                                <rect x="60" y="320" width="480" height="6" fill="#2d333b"/>
                                <rect x="60" y="265" width="480" height="18" fill="#d1d5db"/>
                                <!-- Puerta peatonal (Derecha) -->
                                <rect x="550" y="130" width="190" height="310" fill="#3a414a"/>
                                <rect x="550" y="220" width="190" height="6" fill="#2d333b"/>
                                <rect x="550" y="320" width="190" height="6" fill="#2d333b"/>
                                <rect x="550" y="265" width="190" height="18" fill="#d1d5db"/>
                                <!-- Herrajes y picaporte -->
                                <rect x="570" y="235" width="8" height="70" fill="#d1d5db" rx="4"/>
                                <circle cx="560" cy="270" r="5" fill="#1e2227"/>
                            </svg>
                            <div class="absolute inset-0 bg-brand-blue/20 mix-blend-multiply pointer-events-none"></div>
                        </div>
                    </div>
                    
                    <div class="lg:w-1/2">
                        <h2 class="font-condensed text-4xl md:text-5xl font-bold text-white mb-6 uppercase tracking-wide">El vecino que además es eléctrico</h2>
                        <p class="text-lg text-gray-300 mb-6 leading-relaxed font-medium">
                            En <strong class="text-brand-orange">OpenPort</strong>, entendemos que tu portón no es solo un acceso, es la barrera entre la calle y tu tranquilidad.
                        </p>
                        <p class="text-lg text-gray-300 mb-8 leading-relaxed">
                            Bajo el concepto de la <span class="text-blue-300">"Hora azul"</span>, representamos ese momento de paz al llegar a casa. Somos "El Protector", combinando cercanía de barrio con la más alta técnica y conocimiento.
                        </p>
                        
                        <div class="grid grid-cols-3 gap-4 border-t border-gray-700 pt-8">
                            <div>
                                <p class="font-condensed text-4xl font-bold text-brand-orange mb-1">48 h</p>
                                <p class="font-mono text-xs text-gray-400 uppercase tracking-widest">Instalación</p>
                            </div>
                            <div>
                                <p class="font-condensed text-4xl font-bold text-brand-blue mb-1">24 h</p>
                                <p class="font-mono text-xs text-gray-400 uppercase tracking-widest">Respuesta</p>
                            </div>
                            <div>
                                <p class="font-condensed text-4xl font-bold text-brand-orange mb-1">2</p>
                                <p class="font-mono text-xs text-gray-400 uppercase tracking-widest">Años Garantía</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contacto" class="py-24 bg-gray-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="bg-white rounded-sm overflow-hidden shadow-xl border border-gray-200">
                    <div class="flex flex-col lg:flex-row">
                        <div class="lg:w-5/12 p-10 md:p-16 bg-brand-blue text-white flex flex-col justify-between relative overflow-hidden">
                            <div class="absolute top-0 right-0 -mr-16 -mt-16 w-64 h-64 bg-blue-800 rounded-full blur-3xl opacity-50"></div>
                            <div class="relative z-10">
                                <h3 class="font-condensed text-4xl font-bold mb-4 uppercase tracking-wide">¿Cuánto sale automatizar tu portón?</h3>
                                <p class="text-blue-100 mb-10 text-lg">Dejanos tus datos y te asesoramos para encontrar el motor correcto para tu casa o empresa.</p>
                                
                                <div class="space-y-6 font-mono text-sm">
                                    <div class="flex items-start">
                                        <svg class="w-6 h-6 mt-0.5 mr-4 text-brand-orange" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.243-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                                        <p>Mendoza Capital<br><span class="text-blue-300">Servicio a domicilio</span></p>
                                    </div>
                                    <div class="flex items-center">
                                        <svg class="w-6 h-6 mr-4 text-brand-orange" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51a12.8 12.8 0 00-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
                                        <p>+54 9 261 000-0000</p>
                                    </div>
                                    <div class="flex items-center">
                                        <svg class="w-6 h-6 mr-4 text-brand-orange" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
                                        <p><a href="https://instagram.com/openport.mza" target="_blank" class="hover:text-brand-orange transition-colors">@openport.mza</a></p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <div class="lg:w-7/12 p-10 md:p-16">
                            <form id="contactForm" class="space-y-6" onsubmit="event.preventDefault(); document.getElementById('success-msg').classList.remove('hidden'); this.reset();">
                                <div>
                                    <label for="nombre" class="font-mono block text-xs font-bold text-brand-dark uppercase tracking-wider mb-2">Nombre y Apellido</label>
                                    <input type="text" id="nombre" class="w-full px-4 py-3 bg-gray-50 border border-gray-200 focus:ring-2 focus:ring-brand-orange focus:border-transparent outline-none transition-all rounded-sm" required placeholder="Tu nombre">
                                </div>
                                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                    <div>
                                        <label for="telefono" class="font-mono block text-xs font-bold text-brand-dark uppercase tracking-wider mb-2">Teléfono / WhatsApp</label>
                                        <input type="tel" id="telefono" class="w-full px-4 py-3 bg-gray-50 border border-gray-200 focus:ring-2 focus:ring-brand-orange focus:border-transparent outline-none transition-all rounded-sm" required placeholder="Ej. 261...">
                                    </div>
                                    <div>
                                        <label for="tipo" class="font-mono block text-xs font-bold text-brand-dark uppercase tracking-wider mb-2">Tipo de Portón</label>
                                        <select id="tipo" class="w-full px-4 py-3 bg-gray-50 border border-gray-200 focus:ring-2 focus:ring-brand-orange focus:border-transparent outline-none transition-all rounded-sm text-gray-600">
                                            <option>Corredizo</option>
                                            <option>Levadizo</option>
                                            <option>Pivotante</option>
                                            <option>Reparación / Servicio Técnico</option>
                                            <option>No estoy seguro / Otro</option>
                                        </select>
                                    </div>
                                </div>
                                <div>
                                    <label for="mensaje" class="font-mono block text-xs font-bold text-brand-dark uppercase tracking-wider mb-2">Consultas adicionales (Opcional)</label>
                                    <textarea id="mensaje" rows="3" class="w-full px-4 py-3 bg-gray-50 border border-gray-200 focus:ring-2 focus:ring-brand-orange focus:border-transparent outline-none transition-all resize-none rounded-sm" placeholder="Medidas, problemas actuales, etc."></textarea>
                                </div>
                                <button type="submit" class="w-full bg-brand-orange hover:bg-orange-600 text-white font-mono font-bold py-4 px-6 rounded-sm transition-colors shadow-md hover:shadow-lg text-sm uppercase tracking-widest flex justify-center items-center">
                                    Solicitar Presupuesto 
                                    <svg class="w-5 h-5 ml-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"></path></svg>
                                </button>
                                <div id="success-msg" class="hidden mt-4 p-4 bg-green-50 text-green-700 rounded-sm text-center font-medium border border-green-200">
                                    ¡Gracias! Nos pondremos en contacto a la brevedad.
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="bg-brand-dark text-gray-400 py-12 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center">
            <div class="mb-6 md:mb-0 text-center md:text-left">
                <div class="flex items-center justify-center md:justify-start">
                    <div id="isotipo-footer-container" class="mr-2 flex items-center justify-center bg-white rounded-full p-1 h-12 w-12">
                        <svg viewBox="0 0 100 100" class="h-10 w-10" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M50 10 C27.9 10 10 27.9 10 50 C10 72.1 27.9 90 50 90 C68.5 90 84.1 77.4 88.5 60 L73 60 C69 70 60 76 50 76 C35.6 76 24 64.4 24 50 C24 35.6 35.6 24 50 24 C60 24 69 30 73 40 L88.5 40 C84.1 22.6 68.5 10 50 10 Z" fill="#1E3A8A" stroke="#ffffff" stroke-width="2"/>
                            <path d="M73 45 L90 45 L90 78 C90 81 87 83 84 83 L73 83 Z" fill="#F97316"/>
                            <circle cx="81.5" cy="75" r="3" fill="#ffffff"/>
                        </svg>
                    </div>
                    <span class="font-condensed font-bold text-3xl text-white tracking-wide">OPENPORT</span>
                </div>
                <p class="text-gray-500 font-mono text-xs mt-3 uppercase">El vecino eléctrico © 2026. Mendoza.</p>
            </div>
            
            <div class="flex space-x-6">
                <a href="#" class="text-gray-500 hover:text-brand-orange transition-colors">
                    <span class="sr-only">Instagram OpenPort</span>
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
                </a>
                <a href="#" class="text-gray-500 hover:text-brand-orange transition-colors">
                    <span class="sr-only">WhatsApp</span>
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51a12.8 12.8 0 00-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
                </a>
            </div>
        </div>
    </footer>

    <!-- Botón flotante de WhatsApp animado -->
    <a href="https://wa.me/5492610000000" target="_blank" rel="noopener noreferrer" class="fixed bottom-6 right-6 z-50 bg-[#25D366] text-white p-4 rounded-full shadow-[0_10px_25px_rgba(37,211,102,0.5)] hover:shadow-[0_15px_35px_rgba(37,211,102,0.7)] hover:scale-110 transition-all duration-300 flex items-center justify-center border border-white/30 group animate-bounce" aria-label="Escribinos por WhatsApp">
        <svg class="w-8 h-8 group-hover:animate-pulse" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51a12.8 12.8 0 00-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
    </a>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const btn = document.getElementById('mobile-menu-btn');
            const menu = document.getElementById('mobile-menu');
            const iconBars = document.getElementById('menu-icon-bars');
            const iconClose = document.getElementById('menu-icon-close');

            btn.addEventListener('click', () => {
                menu.classList.toggle('hidden');
                if (menu.classList.contains('hidden')) {
                    iconClose.classList.add('hidden');
                    iconClose.classList.remove('block');
                    iconBars.classList.remove('hidden');
                    iconBars.classList.add('block');
                } else {
                    iconBars.classList.add('hidden');
                    iconBars.classList.remove('block');
                    iconClose.classList.remove('hidden');
                    iconClose.classList.add('block');
                }
            });

            const mobileLinks = menu.querySelectorAll('a');
            mobileLinks.forEach(link => {
                link.addEventListener('click', () => {
                    menu.classList.add('hidden');
                    iconClose.classList.add('hidden');
                    iconClose.classList.remove('block');
                    iconBars.classList.remove('hidden');
                    iconBars.classList.add('block');
                });
            });

            const navbar = document.getElementById('navbar');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 20) {
                    navbar.classList.add('py-0');
                    navbar.classList.remove('py-2');
                } else {
                    navbar.classList.add('py-2');
                    navbar.classList.remove('py-0');
                }
            });
        });
    </script>
</body>
</html>
