<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crave & Cook | Fresh Recipes</title>
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --primary-color: #ff6b6b; /* Appetizing Red/Orange */
            --secondary-color: #333;
            --bg-color: #f9f9f9;
            --card-bg: #ffffff;
            --text-color: #555;
            --font-main: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-main);
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        a { text-decoration: none; color: inherit; }
        ul { list-style: none; }

        /* --- HEADER & NAV --- */
        header {
            background: var(--card-bg);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .btn-subscribe {
            background-color: var(--primary-color);
            color: white;
            padding: 0.5rem 1.2rem;
            border-radius: 25px;
            transition: transform 0.2s;
        }

        .btn-subscribe:hover {
            transform: scale(1.05);
            color: white;
        }

        /* --- HERO SECTION --- */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1498837167922-ddd27525d352?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            height: 60vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 0 1rem;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-btn {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 2rem;
            font-size: 1.1rem;
            border-radius: 5px;
            border: none;
            cursor: pointer;
        }

        /* --- FILTER SECTION --- */
        .filters {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 2rem;
            text-align: center;
        }

        .filter-btn {
            background: transparent;
            border: 2px solid #ddd;
            padding: 0.5rem 1.5rem;
            margin: 0.5rem;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--primary-color);
            border-color: var(--primary-color);
            color: white;
        }

        /* --- RECIPE GRID --- */
        .recipes-container {
            max-width: 1200px;
            margin: 0 auto 4rem auto;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .recipe-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }

        .recipe-card:hover {
            transform: translateY(-5px);
        }

        .recipe-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .recipe-content {
            padding: 1.5rem;
        }

        .recipe-tag {
            font-size: 0.8rem;
            color: var(--primary-color);
            font-weight: bold;
            text-transform: uppercase;
        }

        .recipe-title {
            font-size: 1.4rem;
            margin: 0.5rem 0;
            color: var(--secondary-color);
        }

        .recipe-meta {
            display: flex;
            gap: 1rem;
            font-size: 0.9rem;
            color: #888;
            margin-bottom: 1rem;
        }

        .read-more {
            color: var(--primary-color);
            font-weight: bold;
            border-bottom: 2px solid transparent;
        }
        
        .read-more:hover {
            border-bottom: 2px solid var(--primary-color);
        }

        /* --- FOOTER --- */
        footer {
            background-color: var(--secondary-color);
            color: white;
            text-align: center;
            padding: 3rem 1rem;
        }

        .footer-content h3 {
            margin-bottom: 1rem;
        }

        .socials {
            margin-top: 1rem;
        }
        
        .socials span {
            margin: 0 10px;
            cursor: pointer;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .nav-links { display: none; } /* Simplified for demo */
            .logo { font-size: 1.2rem; }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <nav>
            <div class="logo">Crave & Cook</div>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#">Recipes</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
            <a href="#" class="btn-subscribe">Subscribe</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Discover the Joy of Cooking</h1>
            <p>From quick weeknight dinners to elaborate weekend feasts, find the perfect recipe for every occasion.</p>
            <button class="hero-btn" onclick="document.getElementById('recipes').scrollIntoView({behavior: 'smooth'})">Explore Recipes</button>
        </div>
    </section>

    <!-- Filter Buttons -->
    <section class="filters" id="recipes">
        <button class="filter-btn active" onclick="filterRecipes('all')">All</button>
        <button class="filter-btn" onclick="filterRecipes('breakfast')">Breakfast</button>
        <button class="filter-btn" onclick="filterRecipes('dinner')">Dinner</button>
        <button class="filter-btn" onclick="filterRecipes('dessert')">Dessert</button>
    </section>

    <!-- Recipe Grid -->
    <section class="recipes-container">
        
        <!-- Card 1 -->
        <div class="recipe-card" data-category="breakfast">
            <img src="https://images.unsplash.com/photo-1533089862017-5614ec45e25a?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Pancakes" class="recipe-img">
            <div class="recipe-content">
                <span class="recipe-tag">Breakfast</span>
                <h3 class="recipe-title">Fluffy Blueberry Pancakes</h3>
                <div class="recipe-meta">
                    <span>⏱ 20 mins</span>
                    <span>🔥 Easy</span>
                </div>
                <a href="#" class="read-more">View Recipe →</a>
            </div>
        </div>

        <!-- Card 2 -->
        <div class="recipe-card" data-category="dinner">
            <img src="https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Pizza" class="recipe-img">
            <div class="recipe-content">
                <span class="recipe-tag">Dinner</span>
                <h3 class="recipe-title">Homemade Margherita Pizza</h3>
                <div class="recipe-meta">
                    <span>⏱ 45 mins</span>
                    <span>🔥 Medium</span>
                </div>
                <a href="#" class="read-more">View Recipe →</a>
            </div>
        </div>

        <!-- Card 3 -->
        <div class="recipe-card" data-category="dessert">
            <img src="https://images.unsplash.com/photo-1563729768-6af7c46d6eb1?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Cake" class="recipe-img">
            <div class="recipe-content">
                <span class="recipe-tag">Dessert</span>
                <h3 class="recipe-title">Decadent Chocolate Lava Cake</h3>
                <div class="recipe-meta">
                    <span>⏱ 30 mins</span>
                    <span>🔥 Hard</span>
                </div>
                <a href="#" class="read-more">View Recipe →</a>
            </div>
        </div>

        <!-- Card 4 -->
        <div class="recipe-card" data-category="breakfast">
            <img src="https://images.unsplash.com/photo-1525351484163-7529414395d8?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Avocado Toast" class="recipe-img">
            <div class="recipe-content">
                <span class="recipe-tag">Breakfast</span>
                <h3 class="recipe-title">Avocado Toast with Poached Egg</h3>
                <div class="recipe-meta">
                    <span>⏱ 15 mins</span>
                    <span>🔥 Easy</span>
                </div>
                <a href="#" class="read-more">View Recipe →</a>
            </div>
        </div>

        <!-- Card 5 -->
        <div class="recipe-card" data-category="dinner">
            <img src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Salad" class="recipe-img">
            <div class="recipe-content">
                <span class="recipe-tag">Dinner</span>
                <h3 class="recipe-title">Healthy Quinoa Salad Bowl</h3>
                <div class="recipe-meta">
                    <span>⏱ 25 mins</span>
                    <span>🔥 Easy</span>
                </div>
                <a href="#" class="read-more">View Recipe →</a>
            </div>
        </div>

        <!-- Card 6 -->
        <div class="recipe-card" data-category="dessert">
            <img src="https://images.unsplash.com/photo-1488477181946-6428a0291777?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Ice Cream" class="recipe-img">
            <div class="recipe-content">
                <span class="recipe-tag">Dessert</span>
                <h3 class="recipe-title">Classic Strawberry Ice Cream</h3>
                <div class="recipe-meta">
                    <span>⏱ 4 hrs</span>
                    <span>🔥 Medium</span>
                </div>
                <a href="#" class="read-more">View Recipe →</a>
            </div>
        </div>

    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <h3>Crave & Cook</h3>
            <p>Making the world a tastier place, one recipe at a time.</p>
            <div class="socials">
                <span>Instagram</span>
                <span>Twitter</span>
                <span>Facebook</span>
            </div>
            <p style="margin-top: 2rem; font-size: 0.8rem; opacity: 0.7;">&copy; 2023 Crave & Cook. All rights reserved.</p>
        </div>
    </footer>

    <!-- JavaScript for Filtering -->
    <script>
        function filterRecipes(category) {
            const cards = document.querySelectorAll('.recipe-card');
            const buttons = document.querySelectorAll('.filter-btn');

            // Update active button state
            buttons.forEach(btn => {
                btn.classList.remove('active');
                if(btn.innerText.toLowerCase() === category || (category === 'all' && btn.innerText === 'All')) {
                    btn.classList.add('active');
                }
            });

            // Filter logic
            cards.forEach
