# -<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Global Economic Development Insights</title>
    <style>
        :root {
            --primary: #1e3a8a;
            --secondary: #0ea5e9;
            --accent: #10b981;
            --bg: #f8fafc;
            --text: #1e293b;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 4rem 2rem;
            text-align: center;
        }

        header h1 {
            margin: 0 0 1rem 0;
            font-size: 2.5rem;
        }

        header p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
            opacity: 0.9;
        }

        .container {
            max-width: 1000px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        section {
            background: white;
            margin-bottom: 2rem;
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);
        }

        h2 {
            color: var(--primary);
            margin-top: 0;
            border-bottom: 2px solid var(--bg);
            padding-bottom: 0.5rem;
        }

        .indicators-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .card {
            background: var(--bg);
            padding: 1.5rem;
            border-radius: 8px;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            border-left: 4px solid var(--secondary);
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.05);
        }

        .card h3 {
            margin-top: 0;
            color: var(--primary);
        }

        /* Interactive Simulator Styles */
        .simulator {
            background: #f1f5f9;
            padding: 1.5rem;
            border-radius: 8px;
            margin-top: 1.5rem;
        }

        .input-group {
            margin-bottom: 1rem;
        }

        label {
            display: block;
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        input[type="range"] {
            width: 100%;
            accent-color: var(--secondary);
        }

        .output-box {
            background: white;
            padding: 1rem;
            border-radius: 6px;
            margin-top: 1rem;
            font-weight: bold;
            color: var(--accent);
            text-align: center;
            font-size: 1.2rem;
        }

        footer {
            text-align: center;
            padding: 2rem;
            color: #64748b;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <header>
        <h1>Economic Development</h1>
        <p>Exploring the pathways, metrics, and strategies driving sustainable global growth and improving quality of life.</p>
    </header>

    <div class="container">
        
        <!-- About Section -->
        <section>
            <h2>What is Economic Development?</h2>
            <p>Unlike simple economic growth (which focuses purely on an increase in GDP), <strong>economic development</strong> is a broader qualitative and quantitative process. It focuses on improving the standard of living, enhancing healthcare, expanding education, and ensuring sustainable resource management across a society.</p>
        </section>

        <!-- Interactive Core Pillars -->
        <section>
            <h2>Pillars of Growth</h2>
            <p>Click on any pillar below to reveal its core objective:</p>
            <div class="indicators-grid">
                <div class="card" onclick="toggleDetail(this, 'Infrastructure enables commerce, connects remote regions, and reduces supply chain friction.')">
                    <h3>Infrastructure</h3>
                    <p>Transport, energy, and digital connectivity.</p>
                </div>
                <div class="card" onclick="toggleDetail(this, 'Human Capital focuses on lifelong learning, skill development, and robust public health systems.')">
                    <h3>Human Capital</h3>
                    <p>Education, health, and workforce skills.</p>
                </div>
                <div class="card" onclick="toggleDetail(this, 'Innovation drives long-term productivity gains through technology and research.')">
                    <h3>Innovation & Tech</h3>
                    <p>Research, digital transformation, and R&D.</p>
                </div>
            </div>
            <p id="pillar-detail" style="margin-top: 1.5rem; font-style: italic; color: var(--secondary); min-height: 1.5rem;"></p>
        </section>

        <!-- Interactive JS Tool: Growth Projector -->
        <section>
            <h2>Interactive Growth Simulator</h2>
            <p>Simulate how consistent annual investment affects a nation's projected GDP over a 10-year period.</p>
            
            <div class="simulator">
                <div class="input-group">
                    <label for="initialGdp">Initial GDP ($ Billions): <span id="gdpVal">500</span>B</label>
                    <input type="range" id="initialGdp" min="100" max="2000" step="50" value="500" oninput="calculateGrowth()">
                </div>

                <div class="input-group">
                    <label for="growthRate">Annual Investment Growth Rate (%): <span id="rateVal">4</span>%</label>
                    <input type="range" id="growthRate" min="1" max="10" step="0.5" value="4" oninput="calculateGrowth()">
                </div>

                <div class="output-box" id="resultDisplay">
                    Projected GDP in 10 Years: $740.12 Billion
                </div>
            </div>
        </section>

    </div>

    <footer>
        <p>&copy; 2026 Economic Insights Initiative. Built with HTML, CSS, and JavaScript.</p>
    </footer>

    <!-- JavaScript Logic -->
    <script>
        // Function to handle interactive card clicks
        function toggleDetail(cardElement, text) {
            // Reset background of all cards
            const cards = document.querySelectorAll('.card');
            cards.forEach(c => c.style.background = 'var(--bg)');
            
            // Highlight selected card
            cardElement.style.background = '#e0f2fe';
            
            // Display dynamic message
            document.getElementById('pillar-detail').innerText = "💡 Focus Area: " + text;
        }

        // Function for the live economic growth simulator
        function calculateGrowth() {
            const initialGdp = parseFloat(document.getElementById('initialGdp').value);
            const rate = parseFloat(document.getElementById('growthRate').value) / 100;
            const years = 10;

            // Update range slider text values dynamically
            document.getElementById('gdpVal').innerText = initialGdp;
            document.getElementById('rateVal').innerText = (rate * 100).toFixed(1);

            // Compound growth formula: A = P(1 + r)^t
            const projectedGdp = initialGdp * Math.pow((1 + rate), years);

            // Display result
            document.getElementById('resultDisplay').innerText = 
                `Projected GDP in 10 Years: $${projectedGdp.toFixed(2)} Billion`;
        }

        // Run calculation on page load to sync values
        window.onload = calculateGrowth;
    </script>

</body>
</html>
