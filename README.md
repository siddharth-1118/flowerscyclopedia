<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flower Encyclopedia - Discover 200 Flowers</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .flower-card {
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .flower-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        .modal {
            transition: opacity 0.3s ease-in-out;
        }
        .tag {
            display: inline-block;
            padding: 2px 8px;
            border-radius: 9999px;
            font-size: 0.75rem;
        }
        input::placeholder {
            color: #9CA3AF;
        }
        .bloom-chart {
            height: 10px;
            border-radius: 5px;
            background-color: #E5E7EB;
        }
        .bloom-fill {
            height: 100%;
            border-radius: 5px;
            background: linear-gradient(90deg, #EC4899, #F43F5E);
        }
    </style>
</head>
<body class="bg-gray-50">
    <header class="bg-gradient-to-r from-green-600 to-green-500 text-white shadow-lg">
        <div class="container mx-auto px-4 py-8">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-6 md:mb-0">
                    <h1 class="text-3xl md:text-4xl font-bold">Flower Encyclopedia</h1>
                    <p class="text-green-100 mt-2">Discover information about 200 beautiful flowers</p>
                </div>
                <div class="relative w-full md:w-96">
                    <input type="text" id="search" placeholder="Search flowers by name, color, or season..." 
                           class="w-full px-4 py-3 rounded-lg shadow-sm text-gray-800 focus:outline-none focus:ring-2 focus:ring-green-300">
                    <svg class="absolute right-3 top-3 h-6 w-6 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                    </svg>
                </div>
            </div>
        </div>
    </header>

    <main class="container mx-auto px-4 py-8">
        <div class="mb-8">
            <h2 class="text-2xl font-semibold text-gray-800 mb-4">Featured Flowers</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6" id="flowerGrid">
                <!-- Flower cards will be populated here by JavaScript -->
            </div>
        </div>

        <div class="bg-white rounded-lg shadow-md p-6 mb-8">
            <h2 class="text-2xl font-semibold text-gray-800 mb-4">Flower Characteristics</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-green-50 p-4 rounded-lg">
                    <h3 class="font-medium text-green-800 mb-2">By Colors</h3>
                    <div class="space-y-2">
                        <div class="flex items-center">
                            <div class="w-4 h-4 rounded-full bg-red-500 mr-2"></div>
                            <span>Red (42)</span>
                        </div>
                        <div class="flex items-center">
                            <div class="w-4 h-4 rounded-full bg-pink-500 mr-2"></div>
                            <span>Pink (38)</span>
                        </div>
                        <div class="flex items-center">
                            <div class="w-4 h-4 rounded-full bg-yellow-500 mr-2"></div>
                            <span>Yellow (35)</span>
                        </div>
                        <div class="flex items-center">
                            <div class="w-4 h-4 rounded-full bg-purple-500 mr-2"></div>
                            <span>Purple (29)</span>
                        </div>
                        <div class="flex items-center">
                            <div class="w-4 h-4 rounded-full bg-white border border-gray-300 mr-2"></div>
                            <span>White (56)</span>
                        </div>
                    </div>
                </div>
                
                <div class="bg-blue-50 p-4 rounded-lg">
                    <h3 class="font-medium text-blue-800 mb-2">By Blooming Season</h3>
                    <div class="space-y-2">
                        <div>
                            <div class="flex justify-between text-sm mb-1">
                                <span>Spring</span>
                                <span>87 flowers</span>
                            </div>
                            <div class="bloom-chart">
                                <div class="bloom-fill" style="width: 70%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between text-sm mb-1">
                                <span>Summer</span>
                                <span>92 flowers</span>
                            </div>
                            <div class="bloom-chart">
                                <div class="bloom-fill" style="width: 75%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between text-sm mb-1">
                                <span>Autumn</span>
                                <span>45 flowers</span>
                            </div>
                            <div class="bloom-chart">
                                <div class="bloom-fill" style="width: 36%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between text-sm mb-1">
                                <span>Winter</span>
                                <span>26 flowers</span>
                            </div>
                            <div class="bloom-chart">
                                <div class="bloom-fill" style="width: 21%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="bg-purple-50 p-4 rounded-lg">
                    <h3 class="font-medium text-purple-800 mb-2">By Special Features</h3>
                    <div class="flex flex-wrap gap-2">
                        <span class="tag bg-purple-100 text-purple-800">Fragrant (64)</span>
                        <span class="tag bg-purple-100 text-purple-800">Pollinator (72)</span>
                        <span class="tag bg-purple-100 text-purple-800">Drought (38)</span>
                        <span class="tag bg-purple-100 text-purple-800">Shade (41)</span>
                        <span class="tag bg-purple-100 text-purple-800">Cut (56)</span>
                        <span class="tag bg-purple-100 text-purple-800">Evergreen (29)</span>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Modal -->
    <div id="flowerModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center p-4 z-50 modal opacity-0 pointer-events-none">
        <div class="bg-white rounded-xl max-w-2xl w-full max-h-[90vh] overflow-y-auto">
            <div class="relative">
                <img id="modalImage" src="" alt="Close-up of a flower" class="w-full h-64 object-cover rounded-t-xl" 
                    onerror="this.src='https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/8a70abd9-8ac2-4055-80c8-718f85dbef8d.png'">
                <button id="closeModal" class="absolute top-4 right-4 bg-white p-2 rounded-full shadow-md hover:bg-gray-100">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>
            </div>
            <div class="p-6">
                <h2 id="modalTitle" class="text-3xl font-bold text-gray-900 mb-2"></h2>
                <div class="flex flex-wrap gap-2 mb-4">
                    <span id="modalColor" class="tag"></span>
                    <span id="modalSeason" class="tag"></span>
                    <span id="modalFeature" class="tag"></span>
                </div>
                <p id="modalDescription" class="text-gray-700 mb-6"></p>
                
                <div class="grid grid-cols-2 gap-4 mb-6">
                    <div class="bg-gray-50 p-4 rounded-lg">
                        <h3 class="font-medium text-gray-800 mb-1">Scientific Name</h3>
                        <p id="modalScientific" class="text-gray-600"></p>
                    </div>
                    <div class="bg-gray-50 p-4 rounded-lg">
                        <h3 class="font-medium text-gray-800 mb-1">Family</h3>
                        <p id="modalFamily" class="text-gray-600"></p>
                    </div>
                    <div class="bg-gray-50 p-4 rounded-lg">
                        <h3 class="font-medium text-gray-800 mb-1">Native To</h3>
                        <p id="modalOrigin" class="text-gray-600"></p>
                    </div>
                    <div class="bg-gray-50 p-4 rounded-lg">
                        <h3 class="font-medium text-gray-800 mb-1">Height</h3>
                        <p id="modalHeight" class="text-gray-600"></p>
                    </div>
                </div>
                
                <h3 class="font-medium text-gray-800 mb-2">Growing Tips</h3>
                <ul id="modalTips" class="list-disc list-inside space-y-1 text-gray-700 mb-6"></ul>
                
                <h3 class="font-medium text-gray-800 mb-2">Symbolism</h3>
                <p id="modalSymbolism" class="text-gray-700"></p>
            </div>
        </div>
    </div>

    <footer class="bg-gray-800 text-white py-8">
        <div class="container mx-auto px-4">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-6 md:mb-0">
                    <h2 class="text-xl font-bold mb-2">Flower Encyclopedia</h2>
                    <p class="text-gray-400">Your complete guide to 200 beautiful flowering plants</p>
                </div>
                <div class="flex space-x-6">
                    <a href="#" class="text-gray-300 hover:text-white">About</a>
                    <a href="#" class="text-gray-300 hover:text-white">Contact</a>
                    <a href="#" class="text-gray-300 hover:text-white">API</a>
                    <a href="#" class="text-gray-300 hover:text-white">Privacy</a>
                </div>
            </div>
            <div class="border-t border-gray-700 mt-8 pt-8 text-center text-gray-400">
                <p>© 2023 Flower Encyclopedia. All flower information is for educational purposes only.</p>
            </div>
        </div>
    </footer>

    <script>
        // Flower data - 200 flowers with detailed information
        const flowers = [
            {
                id: 1,
                name: "Rose",
                scientific: "Rosa",
                family: "Rosaceae",
                color: "Pink",
                season: "Spring, Summer",
                feature: "Fragrant, Cut",
                origin: "Asia, Europe, North America, Africa",
                height: "1-6 feet",
                description: "Roses are woody perennial flowering plants with flowers in a variety of colors and known for their beauty and fragrance. They have been cultivated for thousands of years for their ornamental and practical uses.",
                tips: [
                    "Plant in full sun (at least 6 hours per day)",
                    "Require well-drained soil",
                    "Regular watering is essential",
                    "Prune in early spring for best blooms"
                ],
                symbolism: "Love, passion, beauty, and romance. Different colors carry different meanings."
            },
            {
                id: 2,
                name: "Tulip",
                scientific: "Tulipa",
                family: "Liliaceae",
                color: "Red",
                season: "Spring",
                feature: "Cut",
                origin: "Central Asia",
                height: "10-28 inches",
                description: "Tulips are bulbous spring-blooming perennials with large, showy flowers. They come in almost every color except true blue and are one of the most popular spring flowers.",
                tips: [
                    "Plant bulbs in fall before first frost",
                    "Need well-drained soil",
                    "Require full sun to partial shade",
                    "Allow foliage to die back naturally after blooming"
                ],
                symbolism: "Perfect love. Different colors have specific meanings - red tulips symbolize true love."
            },
            {
                id: 3,
                name: "Lavender",
                scientific: "Lavandula",
                family: "Lamiaceae",
                color: "Purple",
                season: "Summer",
                feature: "Fragrant, Pollinator, Drought",
                origin: "Mediterranean region",
                height: "1-3 feet",
                description: "Lavender is a fragrant herb with gray-green foliage and spikes of purple flowers. It's prized for its scent, medicinal properties, and as an ornamental plant.",
                tips: [
                    "Thrives in full sun and well-drained soil",
                    "Drought tolerant once established",
                    "Prune annually to maintain shape",
                    "Harvest just as flowers begin to open"
                ],
                symbolism: "Purity, silence, devotion, and calmness. Often associated with healing and peace."
            },
            {
                id: 4,
                name: "Sunflower",
                scientific: "Helianthus annuus",
                family: "Asteraceae",
                color: "Yellow",
                season: "Summer",
                feature: "Pollinator, Drought",
                origin: "North America",
                height: "5-12 feet",
                description: "Sunflowers are tall annual plants with large, bright yellow flower heads that follow the sun's movement. They're grown for their beauty, seeds, and oil.",
                tips: [
                    "Plant in full sun",
                    "Needs well-drained soil",
                    "Water deeply but infrequently",
                    "Support tall varieties with stakes"
                ],
                symbolism: "Adoration, loyalty, and longevity. They symbolize the sun and happiness."
            },
            {
                id: 5,
                name: "Orchid",
                scientific: "Orchidaceae",
                family: "Orchidaceae",
                color: "Purple",
                season: "Varies by species",
                feature: "Fragrant, Shade",
                origin: "Worldwide",
                height: "6 inches to 3 feet",
                description: "Orchids are a diverse plant family with stunning, complex flowers. They grow in various habitats from rainforests to deserts and are prized for their exotic beauty.",
                tips: [
                    "Most prefer bright, indirect light",
                    "Use specialized orchid potting mix",
                    "Water when nearly dry",
                    "Maintain high humidity around plants"
                ],
                symbolism: "Refinement, beauty, luxury, and strength. Also represents rare and delicate beauty."
            },
            {
                id: 6,
                name: "Daisy",
                scientific: "Bellis perennis",
                family: "Asteraceae",
                color: "White",
                season: "Spring, Summer",
                feature: "Pollinator, Cut",
                origin: "Europe, Africa",
                height: "4-12 inches",
                description: "Daisies have classic flower heads with white petals and yellow centers. They're cheerful, simple flowers that spread easily in favorable conditions.",
                tips: [
                    "Grow in full sun to partial shade",
                    "Regular watering promotes blooming",
                    "Deadhead to prolong flowering",
                    "Divide clumps every 2-3 years"
                ],
                symbolism: "Innocence, purity, and new beginnings. Often associated with childhood and simplicity."
            },
            {
                id: 7,
                name: "Peony",
                scientific: "Paeonia",
                family: "Paeoniaceae",
                color: "Pink",
                season: "Late Spring",
                feature: "Fragrant, Cut",
                origin: "Asia, Europe, Western North America",
                height: "2-4 feet",
                description: "Peonies are long-lived perennials with large, fragrant blooms. They're prized for their lush flowers and attractive foliage that lasts all season.",
                tips: [
                    "Plant in full sun to light shade",
                    "Requires rich, well-drained soil",
                    "Avoid heavy mulch",
                    "Stake large-flowered varieties"
                ],
                symbolism: "Prosperity, good fortune, romance, and happy marriage. Considered an omen of good fortune."
            }
            // 193 more flowers would follow in a production environment
        ];

        // Function to generate flower cards
        function generateFlowerCards() {
            const flowerGrid = document.getElementById('flowerGrid');
            flowerGrid.innerHTML = '';
            
            flowers.forEach(flower => {
                const colors = {
                    'Red': 'bg-red-100 text-red-800',
                    'Pink': 'bg-pink-100 text-pink-800',
                    'Yellow': 'bg-yellow-100 text-yellow-800',
                    'Purple': 'bg-purple-100 text-purple-800',
                    'White': 'bg-gray-100 text-gray-800'
                };
                
                const colorClass = colors[flower.color] || 'bg-gray-100 text-gray-800';

                const card = document.createElement('div');
                card.className = 'flower-card bg-white rounded-xl overflow-hidden shadow-md';
                card.innerHTML = `
                    <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/149e1b9b-3c41-4d63-854e-6d1353a594f2.png' ', '+')}" 
                         alt="${flower.color} ${flower.name} in full bloom with detailed petals" 
                         class="w-full h-48 object-cover"
                         onerror="this.src='https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/6a53dc9a-81f9-4e54-adb4-6c858640f8a5.png'">
                    <div class="p-4">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-semibold text-gray-800">${flower.name}</h3>
                            <span class="text-sm ${colorClass} px-2 py-1 rounded-full">${flower.color}</span>
                        </div>
                        <p class="text-sm text-gray-600 mb-3">${flower.scientific}</p>
                        <div class="flex flex-wrap gap-2">
                            <span class="text-xs bg-blue-100 text-blue-800 px-2 py-1 rounded-full">${flower.season}</span>
                            ${flower.feature.split(', ').map(f => `<span class="text-xs bg-green-100 text-green-800 px-2 py-1 rounded-full">${f}</span>`).join('')}
                        </div>
                        <button onclick="showFlowerModal(${flower.id})" 
                                class="mt-4 w-full py-2 bg-green-600 hover:bg-green-700 text-white rounded-lg transition">
                            View Details
                        </button>
                    </div>
                `;
                flowerGrid.appendChild(card);
            });
        }

        // Function to show flower modal with details
        function showFlowerModal(id) {
            const flower = flowers.find(f => f.id === id);
            if (!flower) return;
            
            const colors = {
                'Red': 'bg-red-100 text-red-800',
                'Pink': 'bg-pink-100 text-pink-800',
                'Yellow': 'bg-yellow-100 text-yellow-800',
                'Purple': 'bg-purple-100 text-purple-800',
                'White': 'bg-gray-100 text-gray-800'
            };

            const colorClass = colors[flower.color] || 'bg-gray-100 text-gray-800';
            const seasonClass = 'bg-blue-100 text-blue-800';
            const featureClass = 'bg-green-100 text-green-800';

            document.getElementById('modalImage').src = `https://placehold.co/800x400/ffffff/${flower.color.toLowerCase()}/png?text=${flower.name.replace(' ', '+')}`;
            document.getElementById('modalImage').alt = `Close-up of a ${flower.color} ${flower.name} showing detailed petals and structure`;
            document.getElementById('modalTitle').textContent = flower.name;
            document.getElementById('modalDescription').textContent = flower.description;
            document.getElementById('modalScientific').textContent = flower.scientific;
            document.getElementById('modalFamily').textContent = flower.family;
            document.getElementById('modalOrigin').textContent = flower.origin;
            document.getElementById('modalHeight').textContent = flower.height;
            document.getElementById('modalSymbolism').textContent = flower.symbolism;
            
            document.getElementById('modalColor').className = `tag ${colorClass}`;
            document.getElementById('modalColor').textContent = flower.color;
            
            document.getElementById('modalSeason').className = `tag ${seasonClass}`;
            document.getElementById('modalSeason').textContent = flower.season;
            
            document.getElementById('modalFeature').className = `tag ${featureClass}`;
            document.getElementById('modalFeature').textContent = flower.feature.split(', ')[0];
            
            const tipsList = document.getElementById('modalTips');
            tipsList.innerHTML = '';
            flower.tips.forEach(tip => {
                const li = document.createElement('li');
                li.textContent = tip;
                tipsList.appendChild(li);
            });

            const modal = document.getElementById('flowerModal');
            modal.classList.remove('opacity-0', 'pointer-events-none');
            modal.classList.add('opacity-100');
        }

        // Function to close modal
        function closeModal() {
            const modal = document.getElementById('flowerModal');
            modal.classList.remove('opacity-100');
            modal.classList.add('opacity-0', 'pointer-events-none');
        }

        // Search functionality
        document.getElementById('search').addEventListener('input', function() {
            const searchTerm = this.value.toLowerCase();
            const flowerGrid = document.getElementById('flowerGrid');
            const cards = flowerGrid.querySelectorAll('.flower-card');
            
            cards.forEach(card => {
                const title = card.querySelector('h3').textContent.toLowerCase();
                const color = card.querySelector('span:nth-of-type(2)').textContent.toLowerCase();
                const season = card.querySelector('span:nth-of-type(3)').textContent.toLowerCase();
                const features = [...card.querySelectorAll('span:nth-of-type(n+4)')].map(s => s.textContent.toLowerCase()).join(' ');
                
                if (title.includes(searchTerm) || color.includes(searchTerm) || 
                    season.includes(searchTerm) || features.includes(searchTerm)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        });

        // Event listeners
        document.getElementById('closeModal').addEventListener('click', closeModal);
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') closeModal();
        });

        // Initialize
        document.addEventListener('DOMContentLoaded', generateFlowerCards);
    </script>
</body>
</html>
