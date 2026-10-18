<html lang="pt-BR" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Impressora Quântica 6D - Sistemas Vivos e Meta-Materiais</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;800;900&family=Rajdhani:wght@300;500;600;700&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cyan: { neon: '#00f3ff' },
                        magenta: { neon: '#ff0055' },
                        gold: { neon: '#ffb700' },
                        emerald: { neon: '#00ff66' },
                        purple: { neon: '#9d00ff' }
                    },
                    fontFamily: {
                        orbitron: ['Orbitron', 'sans-serif'],
                        rajdhani: ['Rajdhani', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #030712;
            color: #e5e7eb;
            font-family: 'Rajdhani', sans-serif;
            overflow-x: hidden;
        }

        /* Glassmorphism & Sci-Fi Borders */
        .hud-panel {
            background: rgba(6, 12, 26, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 243, 255, 0.25);
            box-shadow: 0 0 25px rgba(0, 243, 255, 0.08), inset 0 0 15px rgba(0, 243, 255, 0.03);
        }

        .hud-title {
            font-family: 'Orbitron', sans-serif;
            letter-spacing: 0.08em;
            text-transform: uppercase;
        }

        /* Scanline Overlay */
        .scanline {
            background: linear-gradient(
                to bottom,
                rgba(255,255,255,0),
                rgba(255,255,255,0) 50%,
                rgba(0, 0, 0, 0.35) 50%,
                rgba(0, 0, 0, 0.35)
            );
            background-size: 100% 4px;
            pointer-events: none;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #030712;
        }
        ::-webkit-scrollbar-thumb {
            background: #00f3ff;
            border-radius: 3px;
        }

        /* Range Slider Styling */
        input[type=range] {
            accent-color: #00f3ff;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between selection:bg-cyan-500 selection:text-black">

    <!-- OVERLAY SCANLINES FOR SCI-FI ATMOSPHERE -->
    <div class="fixed inset-0 scanline z-40 opacity-40 pointer-events-none"></div>

    <!-- TOP HUD HEADER -->
    <header class="relative z-30 w-full px-4 py-3 bg-slate-950/90 border-b border-cyan-500/30 backdrop-blur-md flex flex-wrap items-center justify-between gap-4">
        <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-lg border border-cyan-400/60 bg-cyan-950/40 flex items-center justify-center text-cyan-400 text-xl shadow-[0_0_15px_rgba(0,243,255,0.3)]">
                <i class="fa-solid fa-dna animate-pulse"></i>
            </div>
            <div>
                <h1 class="hud-title text-base md:text-xl font-black bg-clip-text text-transparent bg-gradient-to-r from-cyan-400 via-purple-400 to-emerald-400">
                    IMPRESSORA QUÂNTICA 6D — SISTEMAS VIVOS & META-MATERIAIS
                </h1>
                <p class="text-xs text-slate-400 flex items-center gap-2">
                    <span class="inline-block w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
                    EXPANSÃO DA TRÍADE OPERACIONAL: MHD + SAMS + SROS
                </p>
            </div>
        </div>

        <!-- TOP RIGHT ACTION CONTROLS -->
        <div class="flex items-center gap-3 flex-wrap">
            <button id="btnImpactTest" class="px-3.5 py-2 rounded-lg bg-gradient-to-r from-magenta-600/80 to-purple-600/80 hover:from-magenta-500 hover:to-purple-500 border border-magenta-400/60 text-white font-semibold text-xs md:text-sm transition-all shadow-[0_0_15px_rgba(255,0,85,0.3)] flex items-center gap-2">
                <i class="fa-solid fa-bolt text-amber-300"></i>
                Injetar Perturbação de Impacto
            </button>
            <button id="btnOverview" class="px-3.5 py-2 rounded-lg bg-slate-900/90 hover:bg-cyan-950/60 border border-cyan-500/50 text-cyan-300 font-semibold text-xs md:text-sm transition-all shadow-[0_0_15px_rgba(0,243,255,0.2)] flex items-center gap-2">
                <i class="fa-solid fa-book-journal-whills text-cyan-400"></i>
                Base Científica & Visão Geral
            </button>
        </div>
    </header>

    <!-- MAIN DASHBOARD LAYOUT -->
    <main class="relative z-10 flex-1 grid grid-cols-1 lg:grid-cols-12 gap-4 p-4 max-w-[1920px] mx-auto w-full">

        <!-- LEFT PANEL: MODES & TRIAD CONTROL (3 COLS) -->
        <section class="lg:col-span-3 flex flex-col gap-4">

            <!-- MODE SELECTOR -->
            <div class="hud-panel rounded-xl p-4">
                <h2 class="hud-title text-xs text-cyan-400 mb-3 flex items-center gap-2">
                    <i class="fa-solid fa-microscope text-cyan-400"></i> Modo de Operação Quântica
                </h2>
                <div class="space-y-2">
                    <button data-mode="bio" class="mode-btn w-full text-left p-3 rounded-lg border border-cyan-500/50 bg-cyan-950/30 hover:bg-cyan-900/40 transition-all flex items-center justify-between active-mode">
                        <div>
                            <div class="font-bold text-xs text-white">1. Impressão Biológica Atômica</div>
                            <div class="text-[10px] text-slate-400">DNA, Redes Neurais e Músculo Reflexo</div>
                        </div>
                        <i class="fa-solid fa-dna text-emerald-400 text-base"></i>
                    </button>
                    <button data-mode="meta" class="mode-btn w-full text-left p-3 rounded-lg border border-slate-800 bg-slate-900/40 hover:bg-cyan-900/40 transition-all flex items-center justify-between">
                        <div>
                            <div class="font-bold text-xs text-white">2. Meta-Materiais & Levitação MHD</div>
                            <div class="text-[10px] text-slate-400">Cabo Fotônico & Ligas Impossíveis</div>
                        </div>
                        <i class="fa-solid fa-atom text-amber-400 text-base"></i>
                    </button>
                    <button data-mode="shield" class="mode-btn w-full text-left p-3 rounded-lg border border-slate-800 bg-slate-900/40 hover:bg-cyan-900/40 transition-all flex items-center justify-between">
                        <div>
                            <div class="font-bold text-xs text-white">3. Autocultura de Blindagem Ativa</div>
                            <div class="text-[10px] text-slate-400">Escudo de Plasma + Canais SAMS</div>
                        </div>
                        <i class="fa-solid fa-shield-cat text-magenta-400 text-base"></i>
                    </button>
                </div>
            </div>

            <!-- TRIAD TOGGLES & SLIDERS -->
            <div class="hud-panel rounded-xl p-4 flex-1 flex flex-col justify-between">
                <div>
                    <h2 class="hud-title text-xs text-cyan-400 mb-3 flex items-center justify-between">
                        <span><i class="fa-solid fa-sliders text-cyan-400 mr-1.5"></i> Suporte da Tríade Evolutiva</span>
                    </h2>

                    <!-- TRIAD SWITCHES -->
                    <div class="space-y-2.5 mb-4">
                        <div class="p-2.5 rounded-lg border border-amber-500/30 bg-amber-950/10 flex items-center justify-between">
                            <div class="flex items-center gap-2.5">
                                <i class="fa-solid fa-magnet text-amber-400"></i>
                                <div>
                                    <div class="text-xs font-bold text-amber-200">Levitação MHD</div>
                                    <div class="text-[9px] text-slate-400">Contrapressão Magnética</div>
                                </div>
                            </div>
                            <input type="checkbox" id="toggleMHD" checked class="w-4 h-4 accent-amber-400 cursor-pointer">
                        </div>

                        <div class="p-2.5 rounded-lg border border-emerald-500/30 bg-emerald-950/10 flex items-center justify-between">
                            <div class="flex items-center gap-2.5">
                                <i class="fa-solid fa-wave-square text-emerald-400"></i>
                                <div>
                                    <div class="text-xs font-bold text-emerald-200">Amortecimento SAMS</div>
                                    <div class="text-[9px] text-slate-400">Piezoelétricos 1.00G</div>
                                </div>
                            </div>
                            <input type="checkbox" id="toggleSAMS" checked class="w-4 h-4 accent-emerald-400 cursor-pointer">
                        </div>

                        <div class="p-2.5 rounded-lg border border-purple-500/30 bg-purple-950/10 flex items-center justify-between">
                            <div class="flex items-center gap-2.5">
                                <i class="fa-solid fa-network-wired text-purple-400"></i>
                                <div>
                                    <div class="text-xs font-bold text-purple-200">Matriz SROS</div>
                                    <div class="text-[9px] text-slate-400">Emaranhamento Quântico</div>
                                </div>
                            </div>
                            <input type="checkbox" id="toggleSROS" checked class="w-4 h-4 accent-purple-400 cursor-pointer">
                        </div>

                        <div class="p-2.5 rounded-lg border border-magenta-500/30 bg-magenta-950/10 flex items-center justify-between">
                            <div class="flex items-center gap-2.5">
                                <i class="fa-solid fa-shield-halved text-magenta-400"></i>
                                <div>
                                    <div class="text-xs font-bold text-magenta-200">Escudo de Plasma</div>
                                    <div class="text-[9px] text-slate-400">Barreira Defensiva MHD</div>
                                </div>
                            </div>
                            <input type="checkbox" id="togglePlasma" checked class="w-4 h-4 accent-magenta-400 cursor-pointer">
                        </div>
                    </div>

                    <!-- SLIDERS FOR FINE TUNING -->
                    <div class="space-y-3 pt-2 border-t border-slate-800 text-xs">
                        <div>
                            <div class="flex justify-between text-[11px] mb-1">
                                <span class="text-slate-400">Ressonância Quântica (Hz):</span>
                                <span id="valFreq" class="text-cyan-400 font-mono">432.0 GHz</span>
                            </div>
                            <input type="range" id="sliderFreq" min="100" max="900" value="432" class="w-full">
                        </div>

                        <div>
                            <div class="flex justify-between text-[11px] mb-1">
                                <span class="text-slate-400">Intensidade Campo MHD (Tesla):</span>
                                <span id="valField" class="text-amber-400 font-mono">14.5 T</span>
                            </div>
                            <input type="range" id="sliderField" min="1" max="50" value="15" class="w-full">
                        </div>

                        <div>
                            <div class="flex justify-between text-[11px] mb-1">
                                <span class="text-slate-400">Densidade de Plasma Defensivo:</span>
                                <span id="valPlasma" class="text-magenta-400 font-mono">98.5%</span>
                            </div>
                            <input type="range" id="sliderPlasma" min="10" max="100" value="98" class="w-full">
                        </div>
                    </div>
                </div>

                <div id="statusAlert" class="mt-4 p-2.5 rounded-lg border border-emerald-500/40 bg-emerald-950/20 text-emerald-300 text-[11px] flex items-center gap-2">
                    <i class="fa-solid fa-circle-check text-emerald-400"></i>
                    <span>Sistemas Estáveis. Pronto para Impressão Sub-Atômica.</span>
                </div>
            </div>

        </section>

        <!-- CENTER PANEL: HIGH-PERFORMANCE CANVAS 2D (6 COLS) -->
        <section class="lg:col-span-6 flex flex-col gap-3 min-h-[480px] lg:min-h-0">
            <div class="relative flex-1 hud-panel rounded-xl overflow-hidden flex flex-col border border-cyan-500/30">
                
                <!-- CANVAS TOP HUD OVERLAY -->
                <div class="absolute top-3 left-3 right-3 z-20 flex items-center justify-between pointer-events-none">
                    <div class="flex items-center gap-2 bg-slate-950/85 px-3 py-1.5 rounded-lg border border-slate-800">
                        <span class="w-2 h-2 rounded-full bg-cyan-400 animate-ping"></span>
                        <span id="canvasModeLabel" class="text-xs font-bold text-cyan-300 font-mono">MODO 1: BIO-IMPRESSÃO CELULAR / NEURAL</span>
                    </div>
                    <div class="text-xs text-slate-400 font-mono bg-slate-950/85 px-3 py-1.5 rounded-lg border border-slate-800">
                        FPS: <span id="fpsCounter" class="text-emerald-400 font-bold">60</span>
                    </div>
                </div>

                <!-- CANVAS ELEMENT -->
                <canvas id="simCanvas" class="w-full h-full block cursor-crosshair bg-slate-950"></canvas>

                <!-- CANVAS BOTTOM PROGRESS BAR -->
                <div class="p-3 bg-slate-950/90 border-t border-slate-800/80 flex flex-col gap-2 z-20">
                    <div class="flex justify-between items-center text-xs">
                        <span class="text-slate-400 font-semibold flex items-center gap-2">
                            <i class="fa-solid fa-atom animate-spin text-cyan-400"></i>
                            MONITOR DE MONTAGEM ATÔMICA 6D:
                        </span>
                        <span id="printPercent" class="text-cyan-400 font-bold font-mono text-sm">0.0%</span>
                    </div>
                    <div class="w-full h-2.5 bg-slate-900 rounded-full overflow-hidden border border-slate-800 p-0.5">
                        <div id="printProgressBar" class="h-full bg-gradient-to-r from-cyan-500 via-purple-500 to-emerald-400 rounded-full transition-all duration-200" style="width: 0%;"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- RIGHT PANEL: REAL-TIME TELEMETRY & METRICS (3 COLS) -->
        <section class="lg:col-span-3 flex flex-col gap-4">

            <!-- TELEMETRY DASHBOARD -->
            <div class="hud-panel rounded-xl p-4 space-y-3.5">
                <h2 class="hud-title text-xs text-cyan-400 mb-1 flex items-center gap-2">
                    <i class="fa-solid fa-chart-diagram"></i> Telemetria de Processo 6D
                </h2>

                <!-- METRIC 1: ATOMIC ERROR RATE -->
                <div class="bg-slate-900/60 p-2.5 rounded-lg border border-slate-800">
                    <div class="flex justify-between text-xs mb-1">
                        <span class="text-slate-400">Taxa de Erro Atômico:</span>
                        <span id="metricErrorVal" class="text-emerald-400 font-mono font-bold">0.0001%</span>
                    </div>
                    <div class="w-full bg-slate-950 h-1.5 rounded-full overflow-hidden">
                        <div id="barError" class="bg-emerald-400 h-full transition-all duration-300" style="width: 98%;"></div>
                    </div>
                </div>

                <!-- METRIC 2: DNA & PROTEIN INTEGRITY -->
                <div class="bg-slate-900/60 p-2.5 rounded-lg border border-slate-800">
                    <div class="flex justify-between text-xs mb-1">
                        <span class="text-slate-400">Integridade de DNA / Ligas:</span>
                        <span id="metricIntegrityVal" class="text-cyan-300 font-mono font-bold">100.0%</span>
                    </div>
                    <div class="w-full bg-slate-950 h-1.5 rounded-full overflow-hidden">
                        <div id="barIntegrity" class="bg-cyan-400 h-full transition-all duration-300" style="width: 100%;"></div>
                    </div>
                </div>

                <!-- METRIC 3: PHOTONIC CABLE TENSION -->
                <div class="bg-slate-900/60 p-2.5 rounded-lg border border-slate-800">
                    <div class="flex justify-between text-xs mb-1">
                        <span class="text-slate-400">Tensão de Cabo Fotônico:</span>
                        <span id="metricTensionVal" class="text-amber-300 font-mono font-bold">185.4 GPa</span>
                    </div>
                    <div class="w-full bg-slate-950 h-1.5 rounded-full overflow-hidden">
                        <div id="barTension" class="bg-amber-400 h-full transition-all duration-300" style="width: 92%;"></div>
                    </div>
                </div>

                <!-- METRIC 4: PLASMA SHIELD DENSITY -->
                <div class="bg-slate-900/60 p-2.5 rounded-lg border border-slate-800">
                    <div class="flex justify-between text-xs mb-1">
                        <span class="text-slate-400">Barreira de Plasma Defensiva:</span>
                        <span id="metricPlasmaVal" class="text-magenta-300 font-mono font-bold">98.5% (Ativo)</span>
                    </div>
                    <div class="w-full bg-slate-950 h-1.5 rounded-full overflow-hidden">
                        <div id="barPlasma" class="bg-magenta-400 h-full transition-all duration-300" style="width: 98%;"></div>
                    </div>
                </div>

                <!-- METRIC 5: SROS COMPUTE POWER -->
                <div class="bg-slate-900/60 p-2.5 rounded-lg border border-slate-800">
                    <div class="flex justify-between text-xs mb-1">
                        <span class="text-slate-400">Processamento SROS:</span>
                        <span id="metricSROSVal" class="text-purple-300 font-mono font-bold">1.42 PFLOPS Quânticos</span>
                    </div>
                    <div class="w-full bg-slate-950 h-1.5 rounded-full overflow-hidden">
                        <div id="barSROS" class="bg-purple-400 h-full transition-all duration-300" style="width: 95%;"></div>
                    </div>
                </div>
            </div>

            <!-- DYNAMIC EXPLANATION CARD -->
            <div class="hud-panel rounded-xl p-4 flex-1 flex flex-col justify-between">
                <div>
                    <h2 class="hud-title text-xs text-cyan-400 mb-2 flex items-center gap-2">
                        <i class="fa-solid fa-circle-info"></i> Estado do Processo Selecionado
                    </h2>
                    <p id="modeDescription" class="text-xs text-slate-300 leading-relaxed">
                        A estabilização de nível cirúrgico-celular (SAMS + SROS) tece cadeias de DNA, redes neuronais e exoesqueletos musculares sem risco de rejeição imunológica.
                    </p>
                </div>

                <div class="mt-4 pt-3 border-t border-slate-800/80 text-[11px] text-slate-400">
                    <i class="fa-solid fa-circle-nodes text-emerald-400 mr-1"></i>
                    <span id="modeFooterNote">Impressão atômica em andamento sem erros de fase proteica.</span>
                </div>
            </div>

        </section>

    </main>

    <!-- FOOTER HUD -->
    <footer class="relative z-30 px-4 py-2 bg-slate-950/90 border-t border-slate-900 text-slate-500 text-xs flex justify-between items-center">
        <div>Engenharia Quântica Espacial & Biológica © 2026 — Tríade MHD+SAMS+SROS</div>
        <div class="flex gap-4">
            <span class="text-emerald-400"><i class="fa-solid fa-heart-pulse mr-1"></i> Bio-Matriz Ok</span>
            <span class="text-cyan-400"><i class="fa-solid fa-shield-halved mr-1"></i> Plasma Ok</span>
        </div>
    </footer>

    <!-- OVERVIEW / SCIENTIFIC BASE MODAL -->
    <div id="overviewModal" class="fixed inset-0 z-50 bg-black/80 backdrop-blur-md flex items-center justify-center p-4 opacity-0 pointer-events-none transition-all duration-300">
        <div class="hud-panel w-full max-w-4xl max-h-[90vh] rounded-2xl border border-cyan-500/40 p-6 flex flex-col overflow-hidden shadow-[0_0_50px_rgba(0,243,255,0.2)]">
            
            <!-- MODAL HEADER -->
            <div class="flex justify-between items-center border-b border-cyan-500/30 pb-4 mb-4">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-lg bg-cyan-500/20 border border-cyan-400 flex items-center justify-center text-cyan-300 text-xl">
                        <i class="fa-solid fa-atom"></i>
                    </div>
                    <div>
                        <h2 class="hud-title text-lg font-bold text-cyan-300">Base Científica da Impressora 6D Ampliada</h2>
                        <p class="text-xs text-slate-400">Sistemas Vivos, Meta-Materiais & Autocultura de Blindagem Ativa</p>
                    </div>
                </div>
                <button id="btnCloseModal" class="text-slate-400 hover:text-white text-2xl p-2 transition-colors">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <!-- MODAL CONTENT (SCROLLABLE) -->
            <div class="flex-1 overflow-y-auto pr-2 space-y-5 text-sm text-slate-300 leading-relaxed">
                
                <p class="text-xs text-cyan-200 bg-cyan-950/30 p-3 rounded-lg border border-cyan-500/30">
                    Ao expandir a tríade de suporte (<strong>MHD</strong> + <strong>SAMS</strong> + <strong>SROS</strong>) para a medicina celular, infraestrutura planetária, fundição por levitação e escudos de plasma, a Impressora Quântica Espacial 6D torna-se uma <strong>Impressora de Processos e Sistemas Vivos</strong>.
                </p>

                <!-- THREE REVOLUTIONARY CAPACITIES -->
                <div class="space-y-4">
                    
                    <!-- CAPACITY 1 -->
                    <div class="p-4 rounded-xl bg-slate-900/80 border border-emerald-500/30">
                        <h3 class="font-bold text-emerald-300 text-sm flex items-center gap-2 mb-2">
                            <i class="fa-solid fa-dna"></i> 1. Impressão Biológica de Precisão Atômica (Medicina + SROS/SAMS)
                        </h3>
                        <p class="text-xs text-slate-300 mb-2">
                            <strong>A Melhoria:</strong> A estabilização de nível cirúrgico-celular (SAMS + SROS) permite que a impressora atue como uma biomáquina. Ela tece cadeias de DNA, reconstrói redes neuronais e imprime exoesqueletos musculares reflexos integrados ao sistema nervoso do paciente, átomo por átomo.
                        </p>
                        <p class="text-xs text-emerald-400 font-semibold">
                            <strong>O Impacto:</strong> Eliminação completa de rejeições imunológicas ou erros de posicionamento proteico.
                        </p>
                    </div>

                    <!-- CAPACITY 2 -->
                    <div class="p-4 rounded-xl bg-slate-900/80 border border-amber-500/30">
                        <h3 class="font-bold text-amber-300 text-sm flex items-center gap-2 mb-2">
                            <i class="fa-solid fa-flask-vial"></i> 2. Fundição de Meta-Materiais Impossíveis (Levitação MHD + Arquitetura)
                        </h3>
                        <p class="text-xs text-slate-300 mb-2">
                            <strong>A Melhoria:</strong> Usando a fundição por levitação magnética do MHD, a impressora mistura elementos da tabela periódica que normalmente se repelem, criando ligas magnetorreológicas e cabos fotônicos puríssimos no vácuo.
                        </p>
                        <p class="text-xs text-amber-300 font-semibold">
                            <strong>O Impacto:</strong> Fabricação imediata de cabos para Elevadores Espaciais e fundações cinéticas reativas a terremotos e impactos cósmicos.
                        </p>
                    </div>

                    <!-- CAPACITY 3 -->
                    <div class="p-4 rounded-xl bg-slate-900/80 border border-magenta-500/30">
                        <h3 class="font-bold text-magenta-300 text-sm flex items-center gap-2 mb-2">
                            <i class="fa-solid fa-shield-halved"></i> 3. Autocultura de Blindagem Ativa (Escudos de Plasma + SAMS)
                        </h3>
                        <p class="text-xs text-slate-300 mb-2">
                            <strong>A Melhoria:</strong> A impressora fabrica megaestruturas e cascos de naves já integrados com micro-reatores MHD e canais piezoelétricos SAMS diretamente na fuselagem.
                        </p>
                        <p class="text-xs text-magenta-300 font-semibold">
                            <strong>O Impacto:</strong> O objeto impresso nasce capaz de gerar seu próprio escudo de plasma defensivo reativo a projéteis e radiação extrema.
                        </p>
                    </div>

                </div>

            </div>

            <!-- MODAL FOOTER -->
            <div class="mt-4 pt-3 border-t border-cyan-500/30 flex justify-end">
                <button id="btnDismissModal" class="px-5 py-2 rounded-lg bg-cyan-500 hover:bg-cyan-400 text-slate-950 font-bold text-sm transition-all shadow-[0_0_15px_rgba(0,243,255,0.4)]">
                    Entendido / Voltar à Simulação
                </button>
            </div>

        </div>
    </div>

    <!-- JAVASCRIPT ANIMATION ENGINE & SIMULATION -->
    <script>
        window.onload = function() {
            const canvas = document.getElementById('simCanvas');
            const ctx = canvas.getContext('2d');

            // Global State
            const state = {
                mode: 'bio', // 'bio', 'meta', 'shield'
                printProgress: 0.0,
                speedMultiplier: 1.0,
                time: 0,
                impactWave: 0, // Impact ripple effect
                
                // Subsystem Toggles
                mhd: true,
                sams: true,
                sros: true,
                plasma: true,

                // Slider Values
                freq: 432,
                field: 15,
                plasmaDensity: 98,

                // Impact particles
                impactParticles: []
            };

            // Resize Canvas Responsively
            function resizeCanvas() {
                const rect = canvas.getBoundingClientRect();
                canvas.width = rect.width;
                canvas.height = rect.height;
            }
            window.addEventListener('resize', resizeCanvas);
            resizeCanvas();

            // Mode Button Selectors
            document.querySelectorAll('.mode-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    document.querySelectorAll('.mode-btn').forEach(b => {
                        b.classList.remove('border-cyan-500/50', 'bg-cyan-950/30', 'active-mode');
                        b.classList.add('border-slate-800', 'bg-slate-900/40');
                    });
                    const target = e.currentTarget;
                    target.classList.remove('border-slate-800', 'bg-slate-900/40');
                    target.classList.add('border-cyan-500/50', 'bg-cyan-950/30', 'active-mode');

                    state.mode = target.getAttribute('data-mode');
                    state.printProgress = 0.0;
                    updateUIForMode();
                });
            });

            // Toggle Switches
            document.getElementById('toggleMHD').addEventListener('change', (e) => { state.mhd = e.target.checked; updateTelemetry(); });
            document.getElementById('toggleSAMS').addEventListener('change', (e) => { state.sams = e.target.checked; updateTelemetry(); });
            document.getElementById('toggleSROS').addEventListener('change', (e) => { state.sros = e.target.checked; updateTelemetry(); });
            document.getElementById('togglePlasma').addEventListener('change', (e) => { state.plasma = e.target.checked; updateTelemetry(); });

            // Sliders
            document.getElementById('sliderFreq').addEventListener('input', (e) => {
                state.freq = e.target.value;
                document.getElementById('valFreq').innerText = `${state.freq}.0 GHz`;
            });
            document.getElementById('sliderField').addEventListener('input', (e) => {
                state.field = e.target.value;
                document.getElementById('valField').innerText = `${(state.field * 0.97).toFixed(1)} T`;
            });
            document.getElementById('sliderPlasma').addEventListener('input', (e) => {
                state.plasmaDensity = e.target.value;
                document.getElementById('valPlasma').innerText = `${state.plasmaDensity}.0%`;
            });

            // Impact Test Button
            document.getElementById('btnImpactTest').addEventListener('click', () => {
                state.impactWave = 1.0;
                // Generate impact spark particles
                for (let i = 0; i < 30; i++) {
                    state.impactParticles.push({
                        x: canvas.width * 0.5,
                        y: canvas.height * 0.5,
                        vx: (Math.random() - 0.5) * 8,
                        vy: (Math.random() - 0.5) * 8,
                        life: 1.0,
                        color: Math.random() > 0.5 ? '#ff0055' : '#00f3ff'
                    });
                }
            });

            // Modal Triggering
            const modal = document.getElementById('overviewModal');
            document.getElementById('btnOverview').addEventListener('click', () => modal.classList.remove('opacity-0', 'pointer-events-none'));
            document.getElementById('btnCloseModal').addEventListener('click', () => modal.classList.add('opacity-0', 'pointer-events-none'));
            document.getElementById('btnDismissModal').addEventListener('click', () => modal.classList.add('opacity-0', 'pointer-events-none'));

            function updateUIForMode() {
                const label = document.getElementById('canvasModeLabel');
                const desc = document.getElementById('modeDescription');
                const note = document.getElementById('modeFooterNote');

                if (state.mode === 'bio') {
                    label.innerText = 'MODO 1: BIO-IMPRESSÃO CELULAR / NEURAL';
                    desc.innerText = 'A estabilização de nível cirúrgico-celular (SAMS + SROS) tece cadeias de DNA, redes neuronais e exoesqueletos musculares sem risco de rejeição imunológica.';
                    note.innerText = 'Impressão atômica em andamento sem erros de fase proteica.';
                } else if (state.mode === 'meta') {
                    label.innerText = 'MODO 2: META-MATERIAIS & LEVITAÇÃO MHD';
                    desc.innerText = 'Fundição por levitação magnética MHD misturando elementos immiscíveis da tabela periódica para criar cabos fotônicos do Elevador Espacial.';
                    note.innerText = 'Campo de contrapressão magnética ativo. Pureza atômica de 99.999%.';
                } else {
                    label.innerText = 'MODO 3: AUTOCULTURA DE BLINDAGEM ATIVA';
                    desc.innerText = 'Fabricação de fuselagem inteligente com micro-reatores MHD e canais piezoelétricos SAMS para emissão autônoma de escudo de plasma defensivo.';
                    note.innerText = 'Casco reativo gerando barreira contra radiação e impactos cinéticos.';
                }
                updateTelemetry();
            }

            function updateTelemetry() {
                let activeCount = [state.mhd, state.sams, state.sros, state.plasma].filter(Boolean).length;
                const alertBox = document.getElementById('statusAlert');

                if (activeCount === 4) {
                    alertBox.className = "mt-4 p-2.5 rounded-lg border border-emerald-500/40 bg-emerald-950/20 text-emerald-300 text-[11px] flex items-center gap-2";
                    alertBox.innerHTML = `<i class="fa-solid fa-circle-check text-emerald-400"></i><span>Tríade Operacional Integrada. Estabilidade Sub-Atômica Total.</span>`;
                    
                    document.getElementById('metricErrorVal').innerText = '0.0001%';
                    document.getElementById('barError').style.width = '98%';
                    document.getElementById('metricIntegrityVal').innerText = '100.0%';
                    document.getElementById('barIntegrity').style.width = '100%';
                } else {
                    alertBox.className = "mt-4 p-2.5 rounded-lg border border-amber-500/40 bg-amber-950/20 text-amber-300 text-[11px] flex items-center gap-2";
                    alertBox.innerHTML = `<i class="fa-solid fa-triangle-exclamation text-amber-400"></i><span>Sub-Sistemas Desativados. Risco de Erro de Fase Quântica!</span>`;

                    document.getElementById('metricErrorVal').innerText = '4.2500%';
                    document.getElementById('barError').style.width = '35%';
                    document.getElementById('metricIntegrityVal').innerText = '68.4%';
                    document.getElementById('barIntegrity').style.width = '68%';
                }

                document.getElementById('metricTensionVal').innerText = state.mhd ? '185.4 GPa' : '12.0 GPa (Colapso Estático)';
                document.getElementById('barTension').style.width = state.mhd ? '92%' : '15%';

                document.getElementById('metricPlasmaVal').innerText = state.plasma ? `${state.plasmaDensity}.0% (Ativo)` : '0.0% (Inativo)';
                document.getElementById('barPlasma').style.width = state.plasma ? `${state.plasmaDensity}%` : '0%';

                document.getElementById('metricSROSVal').innerText = state.sros ? '1.42 PFLOPS Quânticos' : '0.02 PFLOPS (Local)';
                document.getElementById('barSROS').style.width = state.sros ? '95%' : '10%';
            }

            // FPS Measurement
            let lastTime = performance.now();
            let frameCount = 0;

            // MAIN ANIMATION LOOP
            function animate(now) {
                frameCount++;
                if (now - lastTime >= 1000) {
                    document.getElementById('fpsCounter').innerText = frameCount;
                    frameCount = 0;
                    lastTime = now;
                }

                state.time += 0.02;
                state.printProgress += 0.0015;
                if (state.printProgress > 1.0) state.printProgress = 0.0;

                // Update Progress UI
                const pct = (state.printProgress * 100).toFixed(1);
                document.getElementById('printPercent').innerText = `${pct}%`;
                document.getElementById('printProgressBar').style.width = `${pct}%`;

                // Fade Impact Wave
                if (state.impactWave > 0) state.impactWave -= 0.02;

                // CLEAR CANVAS
                ctx.fillStyle = '#030712';
                ctx.fillRect(0, 0, canvas.width, canvas.height);

                // DRAW SCI-FI GRID & ENVIRONMENT
                drawGrid(ctx, canvas);

                const center = { x: canvas.width * 0.5, y: canvas.height * 0.5 };

                // DRAW SPECIFIC CANVAS MODE
                if (state.mode === 'bio') {
                    drawBioPrintingMode(ctx, center, state);
                } else if (state.mode === 'meta') {
                    drawMetaMaterialsMode(ctx, center, state);
                } else {
                    drawShieldAutocultureMode(ctx, center, state);
                }

                // DRAW IMPACT SPARKS IF ANY
                drawImpactParticles(ctx, state);

                requestAnimationFrame(animate);
            }

            // --- CANVAS RENDERERS ---

            function drawGrid(ctx, canvas) {
                ctx.strokeStyle = 'rgba(0, 243, 255, 0.04)';
                ctx.lineWidth = 1;
                const step = 40;
                for (let x = 0; x < canvas.width; x += step) {
                    ctx.beginPath();
                    ctx.moveTo(x, 0);
                    ctx.lineTo(x, canvas.height);
                    ctx.stroke();
                }
                for (let y = 0; y < canvas.height; y += step) {
                    ctx.beginPath();
                    ctx.moveTo(0, y);
                    ctx.lineTo(canvas.width, y);
                    ctx.stroke();
                }
            }

            // MODE 1: BIO-PRINTING (DNA + NEURAL NET)
            function drawBioPrintingMode(ctx, center, state) {
                const prog = state.printProgress;

                // 1. Render Double Helix DNA strand
                const strandLength = 260;
                const points = 24;
                const amplitude = 35;

                ctx.lineWidth = 2;
                for (let i = 0; i < points * prog; i++) {
                    const t = (i / points);
                    const x = center.x - strandLength / 2 + t * strandLength;
                    const angle = state.time * 2 + i * 0.4;

                    const y1 = center.y + Math.sin(angle) * amplitude;
                    const y2 = center.y - Math.sin(angle) * amplitude;

                    // Base Pair Connector
                    ctx.strokeStyle = 'rgba(0, 243, 255, 0.4)';
                    ctx.beginPath();
                    ctx.moveTo(x, y1);
                    ctx.lineTo(x, y2);
                    ctx.stroke();

                    // Atom Nodes
                    ctx.fillStyle = '#00ff66';
                    ctx.beginPath();
                    ctx.arc(x, y1, 4, 0, Math.PI * 2);
                    ctx.fill();

                    ctx.fillStyle = '#ff0055';
                    ctx.beginPath();
                    ctx.arc(x, y2, 4, 0, Math.PI * 2);
                    ctx.fill();
                }

                // 2. SROS Neural Synapse Nodes
                if (state.sros) {
                    ctx.strokeStyle = 'rgba(157, 0, 255, 0.6)';
                    ctx.lineWidth = 1;
                    for (let i = 0; i < 6; i++) {
                        const nx = center.x + Math.cos(state.time + i) * 120;
                        const ny = center.y + Math.sin(state.time * 1.5 + i) * 80;

                        ctx.beginPath();
                        ctx.moveTo(center.x, center.y);
                        ctx.lineTo(nx, ny);
                        ctx.stroke();

                        ctx.fillStyle = '#9d00ff';
                        ctx.beginPath();
                        ctx.arc(nx, ny, 3, 0, Math.PI * 2);
                        ctx.fill();
                    }
                }
            }

            // MODE 2: META-MATERIALS & MHD LEVITATION
            function drawMetaMaterialsMode(ctx, center, state) {
                const prog = state.printProgress;

                // MHD Levitation Magnetic Lines
                if (state.mhd) {
                    ctx.strokeStyle = 'rgba(255, 183, 0, 0.3)';
                    ctx.lineWidth = 1.5;
                    for (let i = -3; i <= 3; i++) {
                        ctx.beginPath();
                        ctx.arc(center.x, center.y, 70 + i * 15, Math.PI * 0.2, Math.PI * 0.8);
                        ctx.stroke();

                        ctx.beginPath();
                        ctx.arc(center.x, center.y, 70 + i * 15, Math.PI * 1.2, Math.PI * 1.8);
                        ctx.stroke();
                    }
                }

                // Levitating Liquid Alloy Core
                const alloyRadius = 45;
                const grad = ctx.createRadialGradient(center.x, center.y, 5, center.x, center.y, alloyRadius);
                grad.addColorStop(0, '#ffffff');
                grad.addColorStop(0.5, '#ffb700');
                grad.addColorStop(1, '#ff0055');

                ctx.fillStyle = grad;
                ctx.beginPath();
                ctx.arc(center.x, center.y, alloyRadius + Math.sin(state.time * 4) * 3, 0, Math.PI * 2);
                ctx.fill();

                // Extruding Photonic Cable (Space Elevator)
                ctx.strokeStyle = 'rgba(0, 243, 255, 0.9)';
                ctx.lineWidth = 4;
                ctx.beginPath();
                ctx.moveTo(center.x, center.y);
                ctx.lineTo(center.x, center.y + 180 * prog);
                ctx.stroke();
            }

            // MODE 3: SHIELD AUTOCULTURE & PLASMA
            function drawShieldAutocultureMode(ctx, center, state) {
                const prog = state.printProgress;
                const radius = 85;

                // Smart Hull Plate
                ctx.strokeStyle = '#00f3ff';
                ctx.lineWidth = 5;
                ctx.beginPath();
                ctx.arc(center.x, center.y, radius, 0, Math.PI * 2 * prog);
                ctx.stroke();

                // SAMS Piezoelectric Micro-Channels
                if (state.sams) {
                    ctx.strokeStyle = '#00ff66';
                    ctx.lineWidth = 1.5;
                    for (let a = 0; a < Math.PI * 2 * prog; a += 0.4) {
                        const px = center.x + Math.cos(a) * (radius - 8);
                        const py = center.y + Math.sin(a) * (radius - 8);
                        ctx.beginPath();
                        ctx.arc(px, py, 2, 0, Math.PI * 2);
                        ctx.stroke();
                    }
                }

                // Active Plasma Shield Layer
                if (state.plasma) {
                    const plasmaR = radius + 25 + state.impactWave * 20;
                    const pGrad = ctx.createRadialGradient(center.x, center.y, radius, center.x, center.y, plasmaR);
                    pGrad.addColorStop(0, 'rgba(255, 0, 85, 0)');
                    pGrad.addColorStop(0.8, 'rgba(255, 0, 85, 0.2)');
                    pGrad.addColorStop(1, `rgba(255, 0, 85, ${0.7 + state.impactWave * 0.3})`);

                    ctx.fillStyle = pGrad;
                    ctx.beginPath();
                    ctx.arc(center.x, center.y, plasmaR, 0, Math.PI * 2);
                    ctx.fill();

                    ctx.strokeStyle = '#ff0055';
                    ctx.lineWidth = 2;
                    ctx.beginPath();
                    ctx.arc(center.x, center.y, plasmaR, 0, Math.PI * 2);
                    ctx.stroke();
                }
            }

            function drawImpactParticles(ctx, state) {
                for (let i = state.impactParticles.length - 1; i >= 0; i--) {
                    const p = state.impactParticles[i];
                    p.x += p.vx;
                    p.y += p.vy;
                    p.life -= 0.03;

                    if (p.life <= 0) {
                        state.impactParticles.splice(i, 1);
                        continue;
                    }

                    ctx.fillStyle = p.color;
                    ctx.globalAlpha = p.life;
                    ctx.beginPath();
                    ctx.arc(p.x, p.y, 3, 0, Math.PI * 2);
                    ctx.fill();
                }
                ctx.globalAlpha = 1.0;
            }

            // Start Render Loop
            requestAnimationFrame(animate);
        };
    </script>
</body>
</html>
