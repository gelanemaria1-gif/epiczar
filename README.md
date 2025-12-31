<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EPICZAR | Marketplace Premium Moçambicano</title>
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Montserrat:wght@700;800;900&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #FF6B35;
            --primary-dark: #E55A2B;
            --secondary: #2A2D43;
            --accent: #00C9B7;
            --light: #F8F9FF;
            --dark: #1A1C2E;
            --gray: #6C757D;
            --gray-light: #E9ECEF;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            --shadow-hover: 0 20px 50px rgba(0, 0, 0, 0.15);
            --radius: 16px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --header-height: 80px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background: var(--light);
            overflow-x: hidden;
        }
        
        h1, h2, h3, h4 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 800;
            line-height: 1.2;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* ===== HEADER ===== */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: var(--header-height);
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }
        
        .header.scrolled {
            box-shadow: var(--shadow);
            height: 70px;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100%;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
        }
        
        .logo-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
            font-weight: 900;
        }
        
        .logo-text {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.8rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        /* ===== NAVEGAÇÃO ===== */
        .nav-main {
            display: flex;
            align-items: center;
            gap: 30px;
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-link {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            font-size: 1rem;
            position: relative;
            padding: 5px 0;
            transition: var(--transition);
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: var(--transition);
        }
        
        .nav-link:hover {
            color: var(--primary);
        }
        
        .nav-link:hover::after {
            width: 100%;
        }
        
        .header-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        
        .header-action {
            position: relative;
            background: none;
            border: none;
            color: var(--dark);
            font-size: 1.3rem;
            cursor: pointer;
            transition: var(--transition);
            padding: 8px;
            border-radius: 10px;
        }
        
        .header-action:hover {
            color: var(--primary);
            background: var(--gray-light);
        }
        
        .cart-count {
            position: absolute;
            top: -5px;
            right: -5px;
            background: var(--primary);
            color: white;
            font-size: 0.7rem;
            font-weight: 600;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* ===== BOTÕES ===== */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            padding: 12px 24px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.95rem;
            border: none;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.4);
        }
        
        .btn-add-to-cart {
            background: var(--secondary);
            width: 100%;
            justify-content: center;
            margin-top: 15px;
        }
        
        .btn-add-to-cart:hover {
            background: var(--dark);
        }
        
        /* ===== HERO ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: var(--header-height);
            background: linear-gradient(135deg, #1A1C2E 0%, #2A2D43 100%);
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><path fill="%2300C9B7" fill-opacity="0.03" d="M0,0h1000v1000H0V0z"/></svg>');
            background-size: 300px;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 700px;
        }
        
        .hero-title {
            font-size: 4.5rem;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #FF6B35, #00C9B7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero-subtitle {
            font-size: 1.5rem;
            margin-bottom: 30px;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 300;
            line-height: 1.6;
        }
        
        /* ===== PRODUTOS ===== */
        .section {
            padding: 100px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-size: 3.5rem;
            color: var(--secondary);
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: var(--primary);
            border-radius: 2px;
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background: white;
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-hover);
        }
        
        .product-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        
        .product-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: var(--accent);
            color: white;
            padding: 5px 15px;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .product-info {
            padding: 25px;
        }
        
        .product-category {
            color: var(--primary);
            font-size: 0.9rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 10px;
        }
        
        .product-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--secondary);
        }
        
        .product-description {
            color: var(--gray);
            font-size: 0.95rem;
            margin-bottom: 20px;
            line-height: 1.5;
            min-height: 70px;
        }
        
        .product-price {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--primary);
        }
        
        /* ===== MODAIS ===== */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        
        .modal-content {
            background: white;
            border-radius: var(--radius);
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }
        
        .modal-header {
            padding: 25px 30px;
            border-bottom: 1px solid var(--gray-light);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-body {
            padding: 30px;
        }
        
        .modal-footer {
            padding: 25px 30px;
            border-top: 1px solid var(--gray-light);
            background: var(--gray-light);
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--gray);
            cursor: pointer;
        }
        
        /* ===== CARRINHO ===== */
        .cart-empty {
            text-align: center;
            padding: 50px 20px;
            color: var(--gray);
        }
        
        .cart-item {
            display: flex;
            align-items: center;
            gap: 20px;
            padding: 20px 0;
            border-bottom: 1px solid var(--gray-light);
        }
        
        .cart-item-image {
            width: 100px;
            height: 100px;
            object-fit: cover;
            border-radius: 10px;
        }
        
        .cart-item-details {
            flex: 1;
        }
        
        .cart-item-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .cart-item-price {
            color: var(--primary);
            font-weight: 700;
        }
        
        .cart-item-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .quantity-control {
            display: flex;
            align-items: center;
            gap: 10px;
            background: var(--gray-light);
            padding: 5px 15px;
            border-radius: 50px;
        }
        
        .quantity-btn {
            background: none;
            border: none;
            font-size: 1.2rem;
            color: var(--dark);
            cursor: pointer;
            width: 25px;
            height: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }
        
        .cart-summary {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 2px solid var(--dark);
        }
        
        .cart-total {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--primary);
        }
        
        /* ===== ADMIN ===== */
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--secondary);
        }
        
        .form-control {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid var(--gray-light);
            border-radius: var(--radius);
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
        }
        
        textarea.form-control {
            min-height: 120px;
            resize: vertical;
        }
        
        .admin-products-list {
            background: white;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow: hidden;
        }
        
        .admin-product-item {
            display: flex;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid var(--gray-light);
        }
        
        .admin-product-image {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 8px;
            margin-right: 20px;
        }
        
        .admin-actions {
            display: flex;
            gap: 10px;
        }
        
        .btn-delete {
            background: #ff4444;
            color: white;
            padding: 8px 16px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
        }
        
        /* ===== TOAST ===== */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--primary);
            color: white;
            padding: 15px 25px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-hover);
            z-index: 3000;
            transform: translateX(100%);
            transition: transform 0.3s ease;
            max-width: 300px;
        }
        
        .toast.show {
            transform: translateX(0);
        }
        
        /* ===== RESPONSIVIDADE ===== */
        @media (max-width: 768px) {
            .nav-main {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: white;
                padding: 20px;
                box-shadow: var(--shadow);
            }
            
            .nav-main.active {
                display: flex;
            }
            
            .nav-links {
                flex-direction: column;
                width: 100%;
            }
            
            .menu-toggle {
                display: block;
                background: none;
                border: none;
                font-size: 1.5rem;
                color: var(--dark);
                cursor: pointer;
            }
            
            .hero-title {
                font-size: 2.8rem;
            }
            
            .section-title h2 {
                font-size: 2.2rem;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* Login Form Styles */
        .login-instruction {
            text-align: center;
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 20px;
        }
        
        .password-container {
            position: relative;
            margin-bottom: 25px;
        }
        
        .toggle-password {
            position: absolute;
            right: 12px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--gray);
            cursor: pointer;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header" id="header">
        <div class="container header-container">
            <a href="#" class="logo">
                <div class="logo-icon">E</div>
                <div class="logo-text">EPICZAR</div>
            </a>
            
            <button class="menu-toggle" id="menuToggle">
                <i class="fas fa-bars"></i>
            </button>
            
            <nav class="nav-main" id="navMain">
                <div class="nav-links">
                    <a href="#hero" class="nav-link">Início</a>
                    <a href="#products" class="nav-link">Produtos</a>
                    <a href="#contact" class="nav-link">Contato</a>
                </div>
                
                <div class="header-actions">
                    <button class="header-action" id="adminBtn">
                        <i class="fas fa-user-shield"></i>
                    </button>
                    <button class="header-action" id="cartBtn">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </button>
                </div>
            </nav>
        </div>
    </header>

    <!-- Toast -->
    <div class="toast" id="toast"></div>

    <!-- Hero -->
    <section class="hero" id="hero">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">EPICZAR Marketplace</h1>
                <p class="hero-subtitle">
                    A melhor loja online de Moçambique. Compre roupas, ebooks e muito mais com entrega nacional.
                </p>
                <a href="#products" class="btn" style="margin-top: 30px;">
                    <i class="fas fa-shopping-bag"></i> Ver Produtos
                </a>
            </div>
        </div>
    </section>

    <!-- Products -->
    <section class="section" id="products">
        <div class="container">
            <div class="section-title">
                <h2>Nossos Produtos</h2>
                <p>Encontre os melhores produtos com preços especiais</p>
            </div>
            
            <div class="products-grid" id="productsGrid">
                <!-- Produtos carregados via JavaScript -->
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="section" id="contact" style="background: var(--dark); color: white; padding: 60px 0;">
        <div class="container">
            <div style="text-align: center;">
                <h3 style="color: var(--accent); margin-bottom: 20px;">EPICZAR</h3>
                <p style="margin-bottom: 20px; opacity: 0.8;">A sua loja online de confiança em Moçambique</p>
                <p style="opacity: 0.6;">WhatsApp: +258 86 608 0322</p>
                <p style="opacity: 0.6; margin-top: 10px;">© 2024 EPICZAR. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 style="margin: 0;">?? Meu Carrinho</h2>
                <button class="close-modal" onclick="closeModal('cartModal')">×</button>
            </div>
            <div class="modal-body" id="cartItems">
                <!-- Itens do carrinho -->
            </div>
            <div class="modal-footer">
                <div class="cart-summary">
                    <div>
                        <strong>Total:</strong>
                        <div class="cart-total" id="cartTotal">0 MZN</div>
                    </div>
                    <button class="btn" onclick="checkout()">
                        <i class="fas fa-whatsapp"></i> Finalizar no WhatsApp
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Admin Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content" style="max-width: 500px;">
            <div class="modal-header">
                <h2 style="margin: 0;">?? Área Administrativa</h2>
                <button class="close-modal" onclick="closeModal('loginModal')">×</button>
            </div>
            <div class="modal-body">
                <div style="text-align: center; margin-bottom: 30px;">
                    <i class="fas fa-lock" style="font-size: 3rem; color: var(--accent); margin-bottom: 20px;"></i>
                    <h3>Acesso Restrito</h3>
                    <p class="login-instruction">Entre com a senha de administrador</p>
                </div>
                <div class="form-group">
                    <div class="password-container">
                        <input type="password" id="adminPassword" class="form-control" placeholder="Digite a senha" autocomplete="off">
                        <button type="button" class="toggle-password" onclick="togglePasswordVisibility()">
                            <i class="fas fa-eye"></i>
                        </button>
                    </div>
                </div>
                <button class="btn" onclick="login()" style="width: 100%;">
                    <i class="fas fa-sign-in-alt"></i> Entrar
                </button>
            </div>
        </div>
    </div>

    <!-- Admin Panel Modal -->
    <div class="modal" id="adminModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 style="margin: 0;">?? Painel Administrativo</h2>
                <button class="close-modal" onclick="closeModal('adminModal')">×</button>
            </div>
            <div class="modal-body">
                <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 30px;">
                    <div>
                        <h3>Gerenciar Produtos</h3>
                        <p style="color: var(--gray);">Total: <span id="totalProducts">0</span> produtos</p>
                    </div>
                    <button class="btn" onclick="openAddProductModal()">
                        <i class="fas fa-plus"></i> Novo Produto
                    </button>
                </div>
                
                <div class="admin-products-list" id="adminProductsList">
                    <!-- Lista de produtos admin -->
                </div>
            </div>
        </div>
    </div>

    <!-- Add Product Modal -->
    <div class="modal" id="addProductModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 style="margin: 0;">?? Adicionar Produto</h2>
                <button class="close-modal" onclick="closeModal('addProductModal')">×</button>
            </div>
            <div class="modal-body">
                <form id="addProductForm" onsubmit="event.preventDefault(); addProduct();">
                    <div class="form-group">
                        <label class="form-label">Categoria</label>
                        <select id="productCategory" class="form-control" required>
                            <option value="">Selecione uma categoria</option>
                            <option value="ebooks">Ebooks</option>
                            <option value="clothing">Roupas</option>
                            <option value="electronics">Eletrônicos</option>
                            <option value="home">Casa & Decoração</option>
                            <option value="beauty">Beleza & Cuidados</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label">Nome do Produto</label>
                        <input type="text" id="productName" class="form-control" placeholder="Ex: Ebook - Marketing Digital" required>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label">Descrição</label>
                        <textarea id="productDescription" class="form-control" placeholder="Descreva o produto em detalhes..." required></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label">Preço (MZN)</label>
                        <input type="number" id="productPrice" class="form-control" placeholder="Ex: 850" min="0" required>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label">URL da Imagem</label>
                        <input type="url" id="productImage" class="form-control" placeholder="https://exemplo.com/imagem.jpg" required>
                        <small style="color: var(--gray); font-size: 0.85rem; display: block; margin-top: 5px;">
                            Use links de imagens do Unsplash ou outros serviços
                        </small>
                    </div>
                    
                    <button type="submit" class="btn" style="width: 100%; margin-top: 20px;">
                        <i class="fas fa-save"></i> Salvar Produto
                    </button>
                </form>
            </div>
        </div>
    </div>

    <script>
        // ===== CONFIGURAÇÃO =====
        const ADMIN_PASSWORD = "ezateaba"; // SENHA DO ADMIN (NÃO VISÍVEL)
        const WHATSAPP_NUMBER = "258866080322"; // NÚMERO CORRETO SEM ESPAÇOS
        
        // Produtos iniciais
        let products = JSON.parse(localStorage.getItem('epiczar_products')) || [
            {
                id: 1,
                name: "Camiseta Masculina Premium",
                description: "Camiseta de algodão 100% egípcio, confortável e durável. Disponível em várias cores.",
                price: 1200,
                category: "clothing",
                image: "https://images.unsplash.com/photo-1523381294911-8d3cead13475?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 2,
                name: "Ebook - Marketing Digital em Moçambique",
                description: "Guia completo para começar no marketing digital. Estratégias adaptadas ao mercado moçambicano.",
                price: 850,
                category: "ebooks",
                image: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80",
                badge: "Mais Vendido"
            },
            {
                id: 3,
                name: "Fones Bluetooth Premium",
                description: "Fones com cancelamento de ruído ativo, bateria de 30h e qualidade de som excepcional.",
                price: 3500,
                category: "electronics",
                image: "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80",
                badge: "Novo"
            }
        ];
        
        let cart = JSON.parse(localStorage.getItem('epiczar_cart')) || [];
        
        // ===== ELEMENTOS DOM =====
        const cartCount = document.getElementById('cartCount');
        const productsGrid = document.getElementById('productsGrid');
        const cartItems = document.getElementById('cartItems');
        const cartTotal = document.getElementById('cartTotal');
        const toast = document.getElementById('toast');
        const adminProductsList = document.getElementById('adminProductsList');
        const totalProducts = document.getElementById('totalProducts');
        
        // ===== FUNÇÕES GERAIS =====
        function showToast(message) {
            toast.textContent = message;
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 3000);
        }
        
        function openModal(modalId) {
            document.getElementById(modalId).style.display = 'flex';
        }
        
        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }
        
        function updateCartCount() {
            const total = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = total;
            localStorage.setItem('epiczar_cart', JSON.stringify(cart));
        }
        
        function togglePasswordVisibility() {
            const passwordInput = document.getElementById('adminPassword');
            const toggleButton = document.querySelector('.toggle-password i');
            
            if (passwordInput.type === 'password') {
                passwordInput.type = 'text';
                toggleButton.classList.remove('fa-eye');
                toggleButton.classList.add('fa-eye-slash');
            } else {
                passwordInput.type = 'password';
                toggleButton.classList.remove('fa-eye-slash');
                toggleButton.classList.add('fa-eye');
            }
        }
        
        // ===== FUNÇÕES DO CARRINHO =====
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            const existing = cart.find(item => item.id === productId);
            if (existing) {
                existing.quantity += 1;
            } else {
                cart.push({
                    id: product.id,
                    name: product.name,
                    price: product.price,
                    image: product.image,
                    quantity: 1
                });
            }
            
            updateCartCount();
            showToast(`? ${product.name} adicionado ao carrinho!`);
        }
        
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCartCount();
            updateCartModal();
            showToast("Item removido do carrinho");
        }
        
        function updateCartModal() {
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="cart-empty">
                        <i class="fas fa-shopping-cart" style="font-size: 3rem; opacity: 0.3;"></i>
                        <h3>Carrinho vazio</h3>
                        <p>Adicione produtos para continuar</p>
                    </div>
                `;
                cartTotal.textContent = "0 MZN";
                return;
            }
            
            let total = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <img src="${item.image}" alt="${item.name}" class="cart-item-image">
                    <div class="cart-item-details">
                        <h4 class="cart-item-title">${item.name}</h4>
                        <div class="cart-item-price">${item.price} MZN</div>
                        <div class="cart-item-actions">
                            <div class="quantity-control">
                                <button class="quantity-btn" onclick="updateQuantity(${item.id}, ${item.quantity - 1})">-</button>
                                <span>${item.quantity}</span>
                                <button class="quantity-btn" onclick="updateQuantity(${item.id}, ${item.quantity + 1})">+</button>
                            </div>
                            <button class="btn-delete" onclick="removeFromCart(${item.id})">
                                <i class="fas fa-trash"></i> Remover
                            </button>
                        </div>
                    </div>
                    <div style="font-weight: 700; font-size: 1.2rem;">
                        ${itemTotal} MZN
                    </div>
                `;
                cartItems.appendChild(cartItem);
            });
            
            cartTotal.textContent = `${total} MZN`;
        }
        
        function updateQuantity(productId, newQuantity) {
            if (newQuantity < 1) {
                removeFromCart(productId);
                return;
            }
            
            const item = cart.find(item => item.id === productId);
            if (item) {
                item.quantity = newQuantity;
                updateCartCount();
                updateCartModal();
            }
        }
        
        function checkout() {
            if (cart.length === 0) {
                showToast("Adicione produtos ao carrinho primeiro");
                return;
            }
            
            // Formatar mensagem para WhatsApp
            let message = "?? *PEDIDO EPICZAR* ??\n\n";
            message += "Olá! Gostaria de fazer o seguinte pedido:\n\n";
            
            let total = 0;
            
            cart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                message += `*${index + 1}. ${item.name}*\n`;
                message += `   Quantidade: ${item.quantity}\n`;
                message += `   Preço unitário: ${item.price} MZN\n`;
                message += `   Subtotal: ${itemTotal} MZN\n\n`;
            });
            
            message += `----------------\n`;
            message += `*TOTAL: ${total} MZN*\n\n`;
            message += `?? *Meus dados para contato:*\n`;
            message += `(aguardo suas instruções para pagamento)\n\n`;
            message += `Obrigado!`;
            
            // Formatar número corretamente
            const formattedNumber = WHATSAPP_NUMBER.replace(/\s/g, '');
            const whatsappURL = `https://wa.me/${formattedNumber}?text=${encodeURIComponent(message)}`;
            
            // Abrir WhatsApp
            window.open(whatsappURL, '_blank');
            closeModal('cartModal');
        }
        
        // ===== FUNÇÕES DOS PRODUTOS =====
        function renderProducts() {
            productsGrid.innerHTML = '';
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    <img src="${product.image}" alt="${product.name}" class="product-image">
                    <div class="product-info">
                        <div class="product-category">${product.category.toUpperCase()}</div>
                        <h3 class="product-title">${product.name}</h3>
                        <p class="product-description">${product.description}</p>
                        <div class="product-price">${product.price.toLocaleString()} MZN</div>
                        <button class="btn btn-add-to-cart" onclick="addToCart(${product.id})">
                            <i class="fas fa-cart-plus"></i> Adicionar ao Carrinho
                        </button>
                    </div>
                `;
                productsGrid.appendChild(productCard);
            });
        }
        
        function saveProducts() {
            localStorage.setItem('epiczar_products', JSON.stringify(products));
            renderProducts();
            renderAdminProducts();
        }
        
        // ===== FUNÇÕES DO ADMIN =====
        function login() {
            const password = document.getElementById('adminPassword').value;
            
            if (password === ADMIN_PASSWORD) {
                closeModal('loginModal');
                openModal('adminModal');
                renderAdminProducts();
                showToast("Bem-vindo ao painel administrativo!");
                // Limpar campo de senha
                document.getElementById('adminPassword').value = '';
            } else {
                showToast("Senha incorreta! Tente novamente.");
                // Limpar campo de senha
                document.getElementById('adminPassword').value = '';
            }
        }
        
        function renderAdminProducts() {
            adminProductsList.innerHTML = '';
            totalProducts.textContent = products.length;
            
            if (products.length === 0) {
                adminProductsList.innerHTML = '<p style="text-align: center; padding: 40px; color: var(--gray);">Nenhum produto cadastrado</p>';
                return;
            }
            
            products.forEach(product => {
                const item = document.createElement('div');
                item.className = 'admin-product-item';
                item.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="admin-product-image">
                    <div style="flex: 1;">
                        <h4>${product.name}</h4>
                        <p style="color: var(--gray); margin: 5px 0;">${product.description}</p>
                        <div style="color: var(--primary); font-weight: 700;">${product.price.toLocaleString()} MZN</div>
                        <div style="font-size: 0.8rem; color: var(--gray); margin-top: 5px;">
                            ID: ${product.id} | Categoria: ${product.category}
                        </div>
                    </div>
                    <div class="admin-actions">
                        <button class="btn-delete" onclick="deleteProduct(${product.id})">
                            <i class="fas fa-trash"></i> Excluir
                        </button>
                    </div>
                `;
                adminProductsList.appendChild(item);
            });
        }
        
        function openAddProductModal() {
            document.getElementById('addProductForm').reset();
            openModal('addProductModal');
        }
        
        function addProduct() {
            const category = document.getElementById('productCategory').value;
            const name = document.getElementById('productName').value.trim();
            const description = document.getElementById('productDescription').value.trim();
            const price = parseInt(document.getElementById('productPrice').value);
            const image = document.getElementById('productImage').value.trim();
            
            if (!category) {
                showToast("Selecione uma categoria!");
                return;
            }
            
            if (!name || !description || !price || !image) {
                showToast("Preencha todos os campos!");
                return;
            }
            
            if (price < 0) {
                showToast("O preço deve ser positivo!");
                return;
            }
            
            const newProduct = {
                id: Date.now(),
                name,
                description,
                price,
                category,
                image
            };
            
            products.push(newProduct);
            saveProducts();
            closeModal('addProductModal');
            showToast("? Produto adicionado com sucesso!");
        }
        
        function deleteProduct(productId) {
            if (confirm("Tem certeza que deseja excluir este produto?")) {
                products = products.filter(p => p.id !== productId);
                saveProducts();
                showToast("??? Produto excluído com sucesso!");
            }
        }
        
        // ===== EVENT LISTENERS =====
        document.addEventListener('DOMContentLoaded', function() {
            document.getElementById('cartBtn').addEventListener('click', () => {
                updateCartModal();
                openModal('cartModal');
            });
            
            document.getElementById('adminBtn').addEventListener('click', () => {
                openModal('loginModal');
            });
            
            document.getElementById('menuToggle').addEventListener('click', () => {
                document.getElementById('navMain').classList.toggle('active');
            });
            
            // Permitir Enter no login
            document.getElementById('adminPassword').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    login();
                }
            });
            
            // Fechar modais ao clicar fora
            document.querySelectorAll('.modal').forEach(modal => {
                modal.addEventListener('click', (e) => {
                    if (e.target === modal) {
                        modal.style.display = 'none';
                    }
                });
            });
            
            // Fechar menu ao clicar em um link
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', () => {
                    document.getElementById('navMain').classList.remove('active');
                });
            });
            
            // Header scroll effect
            window.addEventListener('scroll', () => {
                const header = document.getElementById('header');
                if (window.scrollY > 50) {
                    header.classList.add('scrolled');
                } else {
                    header.classList.remove('scrolled');
                }
            });
        });
        
        // ===== INICIALIZAÇÃO =====
        window.onload = function() {
            updateCartCount();
            renderProducts();
            
            // Carregar produtos do localStorage se existirem
            if (!localStorage.getItem('epiczar_products')) {
                saveProducts();
            }
        };
    </script>
</body>
</html>
