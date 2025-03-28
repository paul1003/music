<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Where AI Meets Art and Music </title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --primary: #2a2a72;
            --secondary: #aabbcc;
            --accent: #ff6b6b;
            --dark: #232528;
            --light: #f4f4f4;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }

        .navbar {
            background: var(--primary);
            padding: 1rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .navbar ul {
            display: flex;
            justify-content: center;
            list-style: none;
        }

        .navbar a {
            color: white;
            text-decoration: none;
            padding: 1rem 2rem;
            transition: all 0.3s ease;
        }

        .navbar a:hover {
            color: var(--secondary);
        }

        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('music-bg.jpg');
            background-size: cover;
            height: 80vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            margin-top: 60px;
        }

        .products {
            padding: 4rem 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: white;
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 5px;
        }

        .price {
            color: var(--primary);
            font-size: 1.5rem;
            font-weight: bold;
            margin: 1rem 0;
        }

        .btn {
            display: inline-block;
            padding: 0.8rem 1.5rem;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .btn:hover {
            background: var(--primary);
        }

        .section-title {
            text-align: center;
            margin: 3rem 0;
            color: var(--primary);
        }

        .newsletter {
            background: var(--dark);
            color: white;
            padding: 4rem 2rem;
            text-align: center;
        }

        .newsletter input {
            padding: 1rem;
            width: 300px;
            margin: 1rem;
            border: none;
            border-radius: 5px;
        }

        footer {
            background: var(--primary);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <ul>
            <li><a href="#blues">Blues</a></li>
            <li><a href="#love">Love Songs</a></li>
            <li><a href="#ai">AI Tutorials</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section class="hero">
        <div>
            <h1>Digital Harmony</h1>
            <p>Premium Music Albums & AI Production Tutorials</p>
        </div>
    </section>

    <h2 class="section-title" id="blues">Blues Collection</h2>
    <section class="products">
        <div class="product-card">
            <img src="blues-album1.jpg" alt="Blues Album 1" class="product-image">
            <h3>Midnight Blues</h3>
            <p class="price">$14.99</p>
            <button class="btn">Add to Cart</button>
        </div>
        <!-- Add more blues albums here -->
    </section>

    <h2 class="section-title" id="love">Love Songs</h2>
    <section class="products">
        <div class="product-card">
            <img src="love-album1.jpg" alt="Love Album 1" class="product-image">
            <h3>Eternal Romance</h3>
            <p class="price">$12.99</p>
            <button class="btn">Add to Cart</button>
        </div>
        <!-- Add more love song albums here -->
    </section>

    <h2 class="section-title" id="ai">AI Music Tutorials</h2>
    <section class="products">
        <div class="product-card">
            <img src="ai-tutorial1.jpg" alt="AI Tutorial 1" class="product-image">
            <h3>AI Music Production 101</h3>
            <p class="price">$49.99</p>
            <button class="btn">Purchase Course</button>
        </div>
        <!-- Add more tutorials here -->
    </section>

    <section class="newsletter">
        <h2>Subscribe for Updates</h2>
        <input type="email" placeholder="Enter your email">
        <button class="btn">Subscribe</button>
    </section>

    <footer>
        <p>&copy; 2023 Digital Harmony. All rights reserved.</p>
        <div class="social">
            <a href="#"><i class="fab fa-youtube"></i></a>
            <a href="#"><i class="fab fa-spotify"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
    </footer>

    <script>
        // Simple cart functionality
        let cart = [];
        
        document.querySelectorAll('.btn').forEach(button => {
            button.addEventListener('click', () => {
                const product = button.parentElement;
                const item = {
                    title: product.querySelector('h3').textContent,
                    price: product.querySelector('.price').textContent
                };
                cart.push(item);
                alert(`${item.title} added to cart!`);
            });
        });

        // Newsletter form handling
        document.querySelector('.newsletter .btn').addEventListener('click', () => {
            const email = document.querySelector('.newsletter input').value;
            if (validateEmail(email)) {
                alert('Thanks for subscribing!');
            } else {
                alert('Please enter a valid email address');
            }
        });

        function validateEmail(email) {
            const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return re.test(email);
        }
    </script>
</body>
</html>
