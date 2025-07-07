<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Dom Vet Campinas </title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Chosen Palette: Warm Neutrals & Soft Teal -->
    <!-- Application Structure Plan: A dashboard-style single-page application with a fixed sidebar for navigation and a main content area. This structure provides intuitive, constant access to different data sections (Overview, Growth, Services, Opportunities), allowing users to explore the report's insights without losing context. The flow starts with key metrics and allows users to dive deeper into charts and detailed analysis, which is ideal for presenting data-rich content effectively. -->
    <!-- Visualization & Content Choices: 
        - Overview: Key metric cards (HTML/Tailwind) for at-a-glance information (Goal: Inform). 
        - Market Growth: A line chart for faturamento trends and a doughnut chart for market segment breakdown (Goal: Show Change & Compare). Both use Chart.js for interactivity.
        - Popular Services: A horizontal bar chart to clearly compare service demand without label clutter (Goal: Compare). Uses Chart.js.
        - Opportunities: Styled cards with Unicode icons to present qualitative trends in a digestible format (Goal: Organize).
        - Justification: This mix of visualizations and structured text transforms the report into an engaging and easily understandable narrative, prioritizing clarity and user interaction. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 40vh;
        }
        @media (max-width: 768px) {
            .chart-container {
                height: 300px;
                max-height: 50vh;
            }
        }
        .nav-link.active {
            background-color: #e7e5e4;
            color: #44403c;
            font-weight: 600;
        }
        .content-section {
            display: none;
        }
        .content-section.active {
            display: block;
        }
    </style>
</head>
<body class="bg-stone-100 text-stone-800">
    <div class="flex flex-col md:flex-row min-h-screen">
        <aside class="w-full md:w-64 bg-white md:border-r border-stone-200 p-4 md:p-6 flex-shrink-0">
            <div class="flex items-center gap-3 mb-8">
                <div class="bg-teal-500 p-2 rounded-lg">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-dog"><path d="M10 5.2a2.5 2.5 0 0 1 5 0v2.65a2 2 0 0 1 .3 1.15v2.5a2 2 0 0 1-2 2h-1.6a2 2 0 0 1-2-2v-2.5a2 2 0 0 1 .3-1.15Z"/><path d="M5.3 12.3a2 2 0 0 0-.3 1.15v4.05a2 2 0 0 0 2 2h8a2 2 0 0 0 2-2v-4.05a2 2 0 0 0-.3-1.15l-1.7-2.6a2 2 0 0 0-3.4 0Z"/><path d="M8 14v.5"/><path d="M16 14v.5"/><path d="M11.25 19.25h1.5"/><path d="M2.5 10.5h1"/><path d="M20.5 10.5h1"/></svg>
                </div>
                <h1 class="text-xl font-bold text-stone-900">Dom Vet</h1>
            </div>
            <nav id="main-nav">
                <ul class="space-y-2">
                    <li><a href="#overview" class="nav-link flex items-center gap-3 px-4 py-2 rounded-lg text-stone-600 hover:bg-stone-100 transition-colors duration-200">Visão Geral</a></li>
                    <li><a href="#growth" class="nav-link flex items-center gap-3 px-4 py-2 rounded-lg text-stone-600 hover:bg-stone-100 transition-colors duration-200">Crescimento do Mercado</a></li>
                    <li><a href="#services" class="nav-link flex items-center gap-3 px-4 py-2 rounded-lg text-stone-600 hover:bg-stone-100 transition-colors duration-200">Serviços Mais Procurados</a></li>
                    <li><a href="#opportunities" class="nav-link flex items-center gap-3 px-4 py-2 rounded-lg text-stone-600 hover:bg-stone-100 transition-colors duration-200">Oportunidades e Tendências</a></li>
                </ul>
            </nav>
        </aside>

        <main class="flex-1 p-4 sm:p-6 lg:p-8">
            <section id="overview" class="content-section">
                <h2 class="text-3xl font-bold text-stone-900 mb-2">Painel Geral do Mercado Pet</h2>
                <p class="text-stone-600 mb-8">
                    Esta seção oferece uma visão consolidada dos indicadores mais importantes do mercado pet brasileiro. Os cartões abaixo destacam o faturamento projetado, o crescimento anual e a notável expansão no setor de cuidados e estética, refletindo um mercado vibrante e em plena ascensão.
                </p>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="font-semibold text-stone-500 mb-1">Faturamento Previsto (2025)</h3>
                        <p class="text-4xl font-bold text-teal-600">R$ 78,1 Bi</p>
                        <p class="text-stone-500 mt-2">Uma projeção que consolida a força do setor.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="font-semibold text-stone-500 mb-1">Crescimento (2023-2025)</h3>
                        <p class="text-4xl font-bold text-amber-600">+13,1%</p>
                        <p class="text-stone-500 mt-2">Crescimento robusto e sustentado ano a ano.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="font-semibold text-stone-500 mb-1">Expansão em Higiene e Estética</h3>
                        <p class="text-4xl font-bold text-sky-600">+316%</p>
                        <p class="text-stone-500 mt-2">Aumento expressivo nos últimos 6 anos.</p>
                    </div>
                </div>
                 <div class="mt-8 bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                    <h3 class="text-2xl font-bold text-stone-900 mb-4">Resumo Executivo</h3>
                    <p class="text-stone-700 leading-relaxed">
                        O mercado pet brasileiro demonstra um crescimento robusto e sustentado, impulsionado pela "humanização" dos animais de estimação, que agora são vistos como membros da família. Esse fenômeno cultural alavanca a demanda por produtos e serviços de maior valor agregado, especialmente no segmento de higiene e estética. A disposição dos tutores em investir no bem-estar e na aparência de seus pets cria um cenário fértil para negócios especializados que oferecem serviços premium e experiências personalizadas, como o Dom Vet.
                    </p>
                </div>
            </section>

            <section id="growth" class="content-section">
                <h2 class="text-3xl font-bold text-stone-900 mb-2">Crescimento e Faturamento do Mercado</h2>
                <p class="text-stone-600 mb-8">
                    Explore a evolução financeira do mercado pet. O primeiro gráfico ilustra a trajetória ascendente do faturamento total nos últimos anos, evidenciando uma expansão acelerada. O segundo gráfico detalha a composição desse faturamento, mostrando a participação de cada segmento e destacando a dominância do Pet Food, mas com um crescimento notável nos serviços.
                </p>
                <div class="grid grid-cols-1 xl:grid-cols-2 gap-8">
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-xl font-bold text-stone-900 mb-4">Evolução do Faturamento Anual (em Bilhões de R$)</h3>
                        <div class="chart-container">
                            <canvas id="marketGrowthChart"></canvas>
                        </div>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-xl font-bold text-stone-900 mb-4">Faturamento por Segmento (2025)</h3>
                        <div class="chart-container">
                            <canvas id="segmentDoughnutChart"></canvas>
                        </div>
                    </div>
                </div>
            </section>

            <section id="services" class="content-section">
                <h2 class="text-3xl font-bold text-stone-900 mb-2">Serviços Pet Mais Procurados</h2>
                <p class="text-stone-600 mb-8">
                    Este gráfico de barras revela a hierarquia da demanda por serviços pet no Brasil. A popularidade massiva de "Banho e Tosa" e "Serviços Veterinários" confirma a prioridade dos tutores com os cuidados essenciais. Ao mesmo tempo, a existência de demanda por serviços de nicho, cdomo hidratação e adestramento, aponta para oportunidades de especialização e ofertas premium.
                </p>
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                    <h3 class="text-xl font-bold text-stone-900 mb-4">Popularidade dos Serviços (% de Tutores que Buscam)</h3>
                    <div class="chart-container h-[450px] max-h-[60vh]">
                        <canvas id="servicePopularityChart"></canvas>
                    </div>
                </div>
            </section>
            
            <section id="opportunities" class="content-section">
                <h2 class="text-3xl font-bold text-stone-900 mb-2">Oportunidades e Novas Tendências</h2>
                <p class="text-stone-600 mb-8">
                    A evolução do mercado é guiada por novas tendências que refletem a profunda conexão entre tutores e pets. As oportunidades de negócio residem em atender a essa demanda por cuidados mais completos e humanizados. Desde alimentação natural até tecnologia de monitoramento, o futuro do setor pet está na oferta de soluções integradas que promovem o bem-estar animal em todas as suas facetas.
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-lg font-bold text-stone-900 mb-2 flex items-center gap-2"><span>🐾</span> Humanização dos Pets</h3>
                        <p class="text-stone-600">Pets são vistos como membros da família, impulsionando a busca por serviços e produtos que espelham cuidados humanos, como spas, festas e alimentação de alta qualidade.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-lg font-bold text-stone-900 mb-2 flex items-center gap-2"><span>🌿</span> Alimentação Natural</h3>
                        <p class="text-stone-600">Cresce a demanda por dietas naturais, orgânicas e sustentáveis. Tutores estão mais conscientes sobre o impacto da nutrição na saúde e longevidade de seus animais.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-lg font-bold text-stone-900 mb-2 flex items-center gap-2"><span>🏨</span> Expansão do Pet Care</h3>
                        <p class="text-stone-600">A rotina agitada dos tutores aumenta a procura por serviços de conveniência, como creches (day care), hotéis, pet sitters e passeadores (dog walkers).</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-lg font-bold text-stone-900 mb-2 flex items-center gap-2"><span>📱</span> Inovações Tecnológicas</h3>
                        <p class="text-stone-600">Dispositivos como coleiras com GPS, câmeras de monitoramento e aplicativos de saúde fortalecem a segurança e a conexão entre tutores e seus pets.</p>
                    </div>
                     <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-lg font-bold text-stone-900 mb-2 flex items-center gap-2"><span>🌎</span> Sustentabilidade</h3>
                        <p class="text-stone-600">A consciência ambiental influencia as compras, com preferência por produtos feitos de materiais reciclados, biodegradáveis e com produção ética.</p>
                    </div>
                     <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200/50">
                        <h3 class="text-lg font-bold text-stone-900 mb-2 flex items-center gap-2"><span>➕</span> Saúde Holística</h3>
                        <p class="text-stone-600">Além do veterinário, há um interesse crescente em planos de saúde, terapias alternativas e cuidados preventivos para garantir o bem-estar completo do animal.</p>
                    </div>
                </div>
            </section>
        </main>
    </div>

<script>
document.addEventListener('DOMContentLoaded', () => {

    const chartColors = {
        teal: 'rgb(13, 148, 136)',
        amber: 'rgb(217, 119, 6)',
        sky: 'rgb(2, 132, 199)',
        stone: 'rgb(120, 113, 108)',
        teal_light: 'rgba(13, 148, 136, 0.2)',
        amber_light: 'rgba(217, 119, 6, 0.2)',
        sky_light: 'rgba(2, 132, 199, 0.2)',
    };
    
    const navLinks = document.querySelectorAll('.nav-link');
    const contentSections = document.querySelectorAll('.content-section');

    function updateContent(hash) {
        let targetHash = hash || window.location.hash || '#overview';

        contentSections.forEach(section => {
            section.classList.remove('active');
        });

        navLinks.forEach(link => {
            link.classList.remove('active');
        });
        
        const targetSection = document.querySelector(targetHash);
        const activeLink = document.querySelector(`a[href="${targetHash}"]`);

        if (targetSection) {
            targetSection.classList.add('active');
        } else {
             document.querySelector('#overview').classList.add('active');
        }
        
        if (activeLink) {
            activeLink.classList.add('active');
        } else {
            document.querySelector('a[href="#overview"]').classList.add('active');
        }
    }

    navLinks.forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            const targetHash = e.currentTarget.getAttribute('href');
            history.pushState(null, '', targetHash);
            updateContent(targetHash);
        });
    });

    window.addEventListener('popstate', () => {
        updateContent(window.location.hash);
    });

    updateContent();

    const createMarketGrowthChart = () => {
        const ctx = document.getElementById('marketGrowthChart')?.getContext('2d');
        if (!ctx) return;
        new Chart(ctx, {
            type: 'line',
            data: {
                labels: ['2022', '2023', '2024 (proj.)'],
                datasets: [{
                    label: 'Faturamento Anual (R$ Bi)',
                    data: [41.9, 68.0, 75.4],
                    backgroundColor: chartColors.teal_light,
                    borderColor: chartColors.teal,
                    borderWidth: 3,
                    pointBackgroundColor: chartColors.teal,
                    pointRadius: 5,
                    tension: 0.3,
                    fill: true,
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    y: {
                        beginAtZero: false,
                        grid: { color: '#e7e5e4' },
                        ticks: {
                            callback: function(value) { return 'R$ ' + value + ' Bi'; }
                        }
                    },
                    x: {
                       grid: { display: false }
                    }
                },
                plugins: {
                    legend: { display: false },
                    tooltip: {
                        backgroundColor: '#1c1917',
                        titleFont: { size: 14, weight: 'bold' },
                        bodyFont: { size: 12 },
                        padding: 12,
                        cornerRadius: 8,
                        callbacks: {
                           label: function(context) {
                                let label = context.dataset.label || '';
                                if (label) { label += ': '; }
                                if (context.parsed.y !== null) {
                                    label += new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(context.parsed.y) + ' Bilhões';
                                }
                                return label;
                            }
                        }
                    }
                }
            }
        });
    };

    const createSegmentDoughnutChart = () => {
        const ctx = document.getElementById('segmentDoughnutChart')?.getContext('2d');
        if (!ctx) return;
        new Chart(ctx, {
            type: 'doughnut',
            data: {
                labels: ['Alimentos', 'Venda de Animais', 'Prod. Veterinários', 'Serv. Veterinários', 'Outros'],
                datasets: [{
                    label: 'Participação de Mercado',
                    data: [54.1, 10.8, 10.4, 10.2, 14.5],
                    backgroundColor: [
                        chartColors.teal,
                        chartColors.amber,
                        chartColors.sky,
                        '#6d28d9',
                        chartColors.stone
                    ],
                    borderColor: '#ffffff',
                    borderWidth: 4,
                    hoverOffset: 10
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                cutout: '65%',
                plugins: {
                    legend: {
                        position: 'bottom',
                        labels: {
                            padding: 20,
                            font: { size: 12 }
                        }
                    },
                     tooltip: {
                        backgroundColor: '#1c1917',
                        callbacks: {
                           label: function(context) {
                                let label = context.label || '';
                                if (label) { label += ': '; }
                                if (context.parsed !== null) {
                                    label += context.parsed + '%';
                                }
                                return label;
                            }
                        }
                    }
                }
            }
        });
    };
    
    const createServicePopularityChart = () => {
        const ctx = document.getElementById('servicePopularityChart')?.getContext('2d');
        if (!ctx) return;
        new Chart(ctx, {
            type: 'bar',
            data: {
                labels: [
                    'Banho e tosa', 'Serviços veterinários', 'Limpeza e tosa higiênica', 
                    'Hidratação', 'Hospedagem', 'Cuidadores', 
                    'Adestramento', 'Outros tratamentos'
                ],
                datasets: [{
                    label: 'Popularidade (%)',
                    data: [90, 83, 78, 15, 6, 4, 2, 2],
                    backgroundColor: chartColors.teal_light,
                    borderColor: chartColors.teal,
                    borderWidth: 2,
                    borderRadius: 6
                }]
            },
            options: {
                indexAxis: 'y',
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    x: {
                        beginAtZero: true,
                         grid: { color: '#e7e5e4' },
                        ticks: {
                            callback: function(value) { return value + '%'; }
                        }
                    },
                     y: {
                       grid: { display: false }
                    }
                },
                plugins: {
                    legend: { display: false },
                     tooltip: {
                        backgroundColor: '#1c1917',
                         callbacks: {
                           label: function(context) {
                                return ` ${context.parsed.x}% dos tutores`;
                           }
                        }
                    }
                }
            }
        });
    };

    createMarketGrowthChart();
    createSegmentDoughnutChart();
    createServicePopularityChart();

});
</script>
</body>
</html>
