
[magazik7.html](https://github.com/user-attachments/files/22955465/magazik7.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Krempai Store</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            min-height: 100vh;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: white;
        }

        /* Шапка сайта */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background: rgba(22, 33, 62, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 32px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 2px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d, #6bcf7f, #4d96ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.2);
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-link {
            color: white;
            text-decoration: none;
            font-weight: 600;
            font-size: 16px;
            transition: color 0.3s ease;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
        }

        .nav-link:hover {
            color: #ffd93d;
            background: rgba(255, 255, 255, 0.1);
        }

        .auth-buttons {
            display: flex;
            gap: 15px;
        }

        .auth-btn {
            padding: 10px 20px;
            font-size: 16px;
            font-weight: 600;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            color: #16213e;
        }

        .auth-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        /* Основной контент */
        .main-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 100px 20px;
            text-align: center;
        }

        .welcome-text {
            font-size: 48px;
            font-weight: 700;
            margin-bottom: 30px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .subtitle {
            font-size: 20px;
            max-width: 600px;
            line-height: 1.6;
            margin-bottom: 40px;
            color: rgba(255, 255, 255, 0.8);
        }

        /* Секции */
        .section {
            padding: 80px 50px;
            display: none;
        }

        .section.active {
            display: block;
        }

        .section-title {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 40px;
            text-align: center;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Валюта */
        .currency-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .currency-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 25px;
            text-align: center;
            transition: transform 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .currency-item:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.15);
        }

        .currency-amount {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .currency-price {
            font-size: 20px;
            color: #ffd93d;
            margin-bottom: 15px;
        }

        .buy-btn {
            padding: 10px 20px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            color: #16213e;
            border: none;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .buy-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        /* Услуги */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 25px;
            transition: transform 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .service-item:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.15);
        }

        .service-name {
            font-size: 22px;
            font-weight: 700;
            margin-bottom: 15px;
            color: #ffd93d;
        }

        .service-description {
            margin-bottom: 15px;
            line-height: 1.5;
        }

        .service-price {
            font-size: 20px;
            font-weight: 700;
            color: #ff6b6b;
            margin-bottom: 15px;
        }

        /* Отзывы */
        .reviews-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .review-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .review-author {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            margin-right: 15px;
        }

        .author-name {
            font-size: 18px;
            font-weight: 700;
        }

        .review-text {
            line-height: 1.6;
        }

        /* Техподдержка */
        .support-container {
            max-width: 600px;
            margin: 0 auto;
            text-align: center;
        }

        .support-text {
            font-size: 20px;
            margin-bottom: 30px;
            line-height: 1.6;
        }

        .tg-button {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, #0088cc, #00a2ff);
            color: white;
            text-decoration: none;
            border-radius: 10px;
            font-weight: 700;
            font-size: 18px;
            transition: transform 0.3s ease;
        }

        .tg-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 136, 204, 0.4);
        }

        /* Модальные окна */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            padding: 30px;
            border-radius: 15px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .modal h2 {
            text-align: center;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .form-group input {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            background-color: rgba(255, 255, 255, 0.1);
            color: white;
            font-size: 16px;
        }

        .optional {
            font-size: 12px;
            color: rgba(255, 255, 255, 0.6);
            font-style: italic;
        }

        .submit-btn {
            width: 100%;
            padding: 12px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            color: #16213e;
            border: none;
            border-radius: 8px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .close {
            position: absolute;
            top: 15px;
            right: 20px;
            color: white;
            font-size: 30px;
            cursor: pointer;
        }

        /* Окно оплаты */
        .payment-info {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
        }

        .card-number {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 10px;
            letter-spacing: 2px;
        }

        .copy-btn {
            padding: 8px 15px;
            background: linear-gradient(45deg, #6bcf7f, #4d96ff);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
        }

        .payment-text {
            margin-top: 15px;
            line-height: 1.5;
        }

        /* Админ панель */
        .admin-panel {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 25px;
            margin-top: 30px;
            display: none;
        }

        .admin-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 20px;
            color: #ff6b6b;
            text-align: center;
        }

        .orders-list {
            max-height: 300px;
            overflow-y: auto;
        }

        .order-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 10px;
            border-left: 4px solid #ffd93d;
        }

        .order-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }

        .order-product {
            font-weight: 600;
        }

        .order-status {
            padding: 3px 10px;
            border-radius: 15px;
            font-size: 12px;
            font-weight: 600;
        }

        .status-pending {
            background: rgba(255, 219, 61, 0.2);
            color: #ffd93d;
        }

        .status-completed {
            background: rgba(107, 207, 127, 0.2);
            color: #6bcf7f;
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
            display: none;
        }

        .user-greeting {
            font-weight: 600;
        }

        .logout-btn {
            padding: 8px 15px;
            background: linear-gradient(45deg, #ff6b6b, #ffd93d);
            color: #16213e;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
        }
    </style>
</head>
<body>
    <!-- Шапка сайта -->
    <div class="header">
        <div class="logo" id="logo">Krempai Store</div>
        
        <div class="nav-links">
            <div class="nav-link" data-section="currency">Валюта</div>
            <div class="nav-link" data-section="services">Услуги</div>
            <div class="nav-link" data-section="reviews">Отзывы</div>
            <div class="nav-link" data-section="support">Тех поддержка</div>
        </div>
        
        <div class="auth-buttons" id="authButtons">
            <button class="auth-btn" id="loginBtn">Вход</button>
            <button class="auth-btn" id="registerBtn">Регистрация</button>
        </div>
        
        <div class="user-info" id="userInfo">
            <span class="user-greeting">Привет, <span id="userName"></span>!</span>
            <button class="logout-btn" id="logoutBtn">Выйти</button>
        </div>
    </div>

    <!-- Основной контент -->
    <div class="main-content" id="mainContent">
        <h1 class="welcome-text">Добро пожаловать в Krempai Store</h1>
        <p class="subtitle">Лучший магазин для покупки игровой валюты, услуг и многого другого. Безопасные сделки, быстрая доставка и круглосуточная поддержка.</p>
        
        <!-- Админ панель (только для Krempai@gmail.com) -->
        <div class="admin-panel" id="adminPanel">
            <h2 class="admin-title">Панель администратора</h2>
            <div class="orders-list" id="ordersList">
                <!-- Заказы будут добавляться здесь -->
            </div>
        </div>
    </div>

    <!-- Секция Валюта -->
    <div class="section" id="currencySection">
        <h2 class="section-title">Игровая Валюта</h2>
        <div class="currency-grid">
            <div class="currency-item">
                <div class="currency-amount">100кк</div>
                <div class="currency-price">30 грн</div>
                <button class="buy-btn" data-product="100кк" data-price="50">Купить</button>
            </div>
            <div class="currency-item">
                <div class="currency-amount">50кк</div>
                <div class="currency-price">25 грн</div>
                <button class="buy-btn" data-product="50кк" data-price="25">Купить</button>
            </div>
            <div class="currency-item">
                <div class="currency-amount">150кк</div>
                <div class="currency-price">75 грн</div>
                <button class="buy-btn" data-product="150кк" data-price="75">Купить</button>
            </div>
            <div class="currency-item">
                <div class="currency-amount">200кк</div>
                <div class="currency-price">100 грн</div>
                <button class="buy-btn" data-product="200кк" data-price="100">Купить</button>
            </div>
            <div class="currency-item">
                <div class="currency-amount">250кк</div>
                <div class="currency-price">125 грн</div>
                <button class="buy-btn" data-product="250кк" data-price="125">Купить</button>
            </div>
            <div class="currency-item">
                <div class="currency-amount">300кк</div>
                <div class="currency-price">150 грн</div>
                <button class="buy-btn" data-product="300кк" data-price="150">Купить</button>
            </div>
        </div>
    </div>

    <!-- Секция Услуги -->
    <div class="section" id="servicesSection">
        <h2 class="section-title">Услуги</h2>
        <div class="services-grid">
            <div class="service-item">
                <div class="service-name">Постройка фармилки криперов</div>
                <div class="service-description">Строительство эффективной фармилки криперов для получения большого количества пороха.</div>
                <div class="service-price">100 грн</div>
                <button class="buy-btn" data-product="Постройка фармилки криперов" data-price="100">Купить</button>
            </div>
            <div class="service-item">
                <div class="service-name">Постройка фармилки криперов 50/50</div>
                <div class="service-description">Улучшенная версия фармилки с увеличенной эффективностью и надежностью.</div>
                <div class="service-price">200 грн</div>
                <button class="buy-btn" data-product="Постройка фармилки криперов 50/50" data-price="200">Купить</button>
            </div>
            <div class="service-item">
                <div class="service-name">Постройка зельеварки</div>
                <div class="service-description">Создание автоматизированной зельеварки для приготовления различных зелий.</div>
                <div class="service-price">150 грн</div>
                <button class="buy-btn" data-product="Постройка зельеварки" data-price="150">Купить</button>
            </div>
        </div>
    </div>

    <!-- Секция Отзывы -->
    <div class="section" id="reviewsSection">
        <h2 class="section-title">Отзывы</h2>
        <div class="reviews-container">
            <div class="review-item">
                <div class="review-author">
                    <div class="author-avatar">B</div>
                    <div class="author-name">Bro9i</div>
                </div>
                <div class="review-text">
                    Отличный магазин! Купил 100кк валюты, все пришло мгновенно. Очень доволен обслуживанием и скоростью доставки. Рекомендую!
                </div>
            </div>
            <div class="review-item">
                <div class="review-author">
                    <div class="author-avatar">F</div>
                    <div class="author-name">Fluger</div>
                </div>
                <div class="review-text">
                    Заказывал постройку фармилки криперов. Сделали все качественно и быстро. Теперь у меня много пороха для крафта! Спасибо Krempai Store!
                </div>
            </div>
        </div>
    </div>

    <!-- Секция Техподдержка -->
    <div class="section" id="supportSection">
        <h2 class="section-title">Техническая Поддержка</h2>
        <div class="support-container">
            <p class="support-text">
                Если у вас возникли вопросы или проблемы, наши специалисты всегда готовы помочь. Напишите нам в Telegram, и мы оперативно решим ваш вопрос.
            </p>
            <a href="https://t.me/KrempaiiiMZ" class="tg-button" target="_blank">Написать в Telegram</a>
        </div>
    </div>

    <!-- Модальные окна -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <span class="close" id="closeLogin">&times;</span>
            <h2>Вход в аккаунт</h2>
            <form id="loginForm">
                <div class="form-group">
                    <label for="loginEmail">Email:</label>
                    <input type="email" id="loginEmail" required>
                </div>
                <div class="form-group">
                    <label for="loginPassword">Пароль:</label>
                    <input type="password" id="loginPassword" required>
                </div>
                <button type="submit" class="submit-btn">Войти</button>
            </form>
        </div>
    </div>

    <div class="modal" id="registerModal">
        <div class="modal-content">
            <span class="close" id="closeRegister">&times;</span>
            <h2>Регистрация</h2>
            <form id="registerForm">
                <div class="form-group">
                    <label for="registerName">Имя:</label>
                    <input type="text" id="registerName" required>
                </div>
                <div class="form-group">
                    <label for="registerEmail">Email:</label>
                    <input type="email" id="registerEmail" required>
                </div>
                <div class="form-group">
                    <label for="registerPassword">Пароль:</label>
                    <input type="password" id="registerPassword" required>
                </div>
                <button type="submit" class="submit-btn">Зарегистрироваться</button>
            </form>
        </div>
    </div>

    <!-- Модальное окно оплаты -->
    <div class="modal" id="paymentModal">
        <div class="modal-content">
            <span class="close" id="closePayment">&times;</span>
            <h2>Оформление заказа</h2>
            
            <div class="payment-info">
                <div class="card-number" id="cardNumber">5375 4141 1234 5678</div>
                <button class="copy-btn" id="copyCardBtn">Скопировать</button>
                <div class="payment-text">
                    Переведите <span id="paymentAmount">0</span> грн на указанную карту. После оплаты пришлите скриншот чека в техподдержку.
                </div>
            </div>
            
            <form id="orderForm">
                <div class="form-group">
                    <label for="serverNickname">Ваш ник на сервере:</label>
                    <input type="text" id="serverNickname" required>
                </div>
                <div class="form-group">
                    <label for="promoCode">Промокод: <span class="optional">(не обязательно)</span></label>
                    <input type="text" id="promoCode">
                </div>
                <button type="submit" class="submit-btn">Подтвердить заказ</button>
            </form>
        </div>
    </div>

    <script>
        // Элементы DOM
        const logo = document.getElementById('logo');
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const loginModal = document.getElementById('loginModal');
        const registerModal = document.getElementById('registerModal');
        const paymentModal = document.getElementById('paymentModal');
        const closeLogin = document.getElementById('closeLogin');
        const closeRegister = document.getElementById('closeRegister');
        const closePayment = document.getElementById('closePayment');
        const loginForm = document.getElementById('loginForm');
        const registerForm = document.getElementById('registerForm');
        const orderForm = document.getElementById('orderForm');
        const userInfo = document.getElementById('userInfo');
        const userName = document.getElementById('userName');
        const logoutBtn = document.getElementById('logoutBtn');
        const authButtons = document.getElementById('authButtons');
        const mainContent = document.getElementById('mainContent');
        const navLinks = document.querySelectorAll('.nav-link');
        const sections = document.querySelectorAll('.section');
        const buyButtons = document.querySelectorAll('.buy-btn');
        const paymentAmount = document.getElementById('paymentAmount');
        const cardNumber = document.getElementById('cardNumber');
        const copyCardBtn = document.getElementById('copyCardBtn');
        const adminPanel = document.getElementById('adminPanel');
        const ordersList = document.getElementById('ordersList');

        // Текущий выбранный товар
        let currentProduct = null;
        let currentPrice = null;

        // Прокрутка к началу страницы при клике на логотип
        logo.addEventListener('click', () => {
            window.scrollTo({ top: 0, behavior: 'smooth' });
            showSection('main');
        });

        // Навигация по разделам
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                const section = link.getAttribute('data-section');
                showSection(section);
            });
        });

        // Функция показа раздела
        function showSection(sectionId) {
            // Скрыть все секции
            sections.forEach(section => {
                section.classList.remove('active');
            });
            mainContent.style.display = 'none';
            
            // Показать выбранную секцию
            if (sectionId === 'main') {
                mainContent.style.display = 'flex';
            } else {
                document.getElementById(sectionId + 'Section').classList.add('active');
            }
            
            // Прокрутить к началу
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Обработка кнопок "Купить"
        buyButtons.forEach(button => {
            button.addEventListener('click', () => {
                currentProduct = button.getAttribute('data-product');
                currentPrice = button.getAttribute('data-price');
                
                paymentAmount.textContent = currentPrice;
                paymentModal.style.display = 'flex';
            });
        });

        // Копирование номера карты
        copyCardBtn.addEventListener('click', () => {
            navigator.clipboard.writeText(cardNumber.textContent)
                .then(() => {
                    copyCardBtn.textContent = 'Скопировано!';
                    setTimeout(() => {
                        copyCardBtn.textContent = 'Скопировать';
                    }, 2000);
                })
                .catch(err => {
                    console.error('Ошибка копирования: ', err);
                });
        });

        // Оформление заказа
        orderForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const nickname = document.getElementById('serverNickname').value;
            const promoCode = document.getElementById('promoCode').value;
            
            // Создание заказа
            const order = {
                id: Date.now(),
                product: currentProduct,
                price: currentPrice,
                nickname: nickname,
                promoCode: promoCode,
                status: 'pending',
                date: new Date().toLocaleString()
            };
            
            // Сохранение заказа
            const orders = JSON.parse(localStorage.getItem('orders')) || [];
            orders.push(order);
            localStorage.setItem('orders', JSON.stringify(orders));
            
            // Обновление админ панели
            updateAdminPanel();
            
            // Закрытие модального окна
            paymentModal.style.display = 'none';
            orderForm.reset();
            
            alert('Заказ успешно оформлен! После оплаты пришлите скриншот в техподдержку.');
        });

        // Проверка авторизации при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            const user = JSON.parse(localStorage.getItem('currentUser'));
            if (user) {
                showUserInfo(user);
                
                // Показать админ панель для Krempai@gmail.com
                if (user.email === 'Krempai@gmail.com') {
                    adminPanel.style.display = 'block';
                    updateAdminPanel();
                }
            }
        });

        // Открытие модальных окон
        loginBtn.addEventListener('click', () => {
            loginModal.style.display = 'flex';
        });

        registerBtn.addEventListener('click', () => {
            registerModal.style.display = 'flex';
        });

        // Закрытие модальных окон
        closeLogin.addEventListener('click', () => {
            loginModal.style.display = 'none';
        });

        closeRegister.addEventListener('click', () => {
            registerModal.style.display = 'none';
        });

        closePayment.addEventListener('click', () => {
            paymentModal.style.display = 'none';
        });

        // Закрытие модальных окон при клике вне их
        window.addEventListener('click', (e) => {
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
            if (e.target === registerModal) {
                registerModal.style.display = 'none';
            }
            if (e.target === paymentModal) {
                paymentModal.style.display = 'none';
            }
        });

        // Обработка формы входа
        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            // Получаем пользователей из localStorage
            const users = JSON.parse(localStorage.getItem('users')) || [];
            
            // Проверяем существование пользователя
            const user = users.find(u => u.email === email && u.password === password);
            
            if (user) {
                // Сохраняем текущего пользователя
                localStorage.setItem('currentUser', JSON.stringify(user));
                showUserInfo(user);
                
                // Показать админ панель для Krempai@gmail.com
                if (user.email === 'Krempai@gmail.com') {
                    adminPanel.style.display = 'block';
                    updateAdminPanel();
                }
                
                loginModal.style.display = 'none';
                loginForm.reset();
            } else {
                alert('Неверный email или пароль!');
            }
        });

        // Обработка формы регистрации
        registerForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const name = document.getElementById('registerName').value;
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            
            // Получаем пользователей из localStorage
            const users = JSON.parse(localStorage.getItem('users')) || [];
            
            // Проверяем, не зарегистрирован ли уже такой email
            if (users.find(u => u.email === email)) {
                alert('Пользователь с таким email уже зарегистрирован!');
                return;
            }
            
            // Добавляем нового пользователя
            const newUser = { name, email, password };
            users.push(newUser);
            localStorage.setItem('users', JSON.stringify(users));
            
            // Автоматически входим после регистрации
            localStorage.setItem('currentUser', JSON.stringify(newUser));
            showUserInfo(newUser);
            
            // Показать админ панель для Krempai@gmail.com
            if (newUser.email === 'Krempai@gmail.com') {
                adminPanel.style.display = 'block';
                updateAdminPanel();
            }
            
            registerModal.style.display = 'none';
            registerForm.reset();
            
            alert('Регистрация прошла успешно!');
        });

        // Выход из аккаунта
        logoutBtn.addEventListener('click', () => {
            localStorage.removeItem('currentUser');
            userInfo.style.display = 'none';
            authButtons.style.display = 'flex';
            adminPanel.style.display = 'none';
        });

        // Показать информацию о пользователе
        function showUserInfo(user) {
            userName.textContent = user.name;
            userInfo.style.display = 'flex';
            authButtons.style.display = 'none';
        }

        // Обновление админ панели
        function updateAdminPanel() {
            const orders = JSON.parse(localStorage.getItem('orders')) || [];
            
            if (orders.length === 0) {
                ordersList.innerHTML = '<p>Заказов пока нет</p>';
                return;
            }
            
            ordersList.innerHTML = '';
            orders.forEach(order => {
                const orderElement = document.createElement('div');
                orderElement.className = 'order-item';
                orderElement.innerHTML = `
                    <div class="order-info">
                        <span class="order-product">${order.product}</span>
                        <span class="order-status ${order.status === 'pending' ? 'status-pending' : 'status-completed'}">${order.status === 'pending' ? 'Ожидает оплаты' : 'Выполнен'}</span>
                    </div>
                    <div>Ник: ${order.nickname}</div>
                    <div>Сумма: ${order.price} грн</div>
                    <div>Дата: ${order.date}</div>
                    ${order.promoCode ? `<div>Промокод: ${order.promoCode}</div>` : ''}
                `;
                ordersList.appendChild(orderElement);
            });
        }
    </script>
</body>
</html>
