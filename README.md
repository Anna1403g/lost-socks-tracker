<!DOCTYPE html>
<html lang="uk">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тазіки Shop – Купити тазік</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
        }

        header {
            background: #009688;
            color: white;
            padding: 15px;
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            z-index: 1000;
        }

        nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        nav ul li {
            display: inline;
            margin: 0 15px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-size: 18px;
        }

        .section {
            padding: 80px 20px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .hero {
            background: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTJkSUD_6Q3qcPma1FtoGkPD9XBiUZvFR6Rjw&s') no-repeat center center/cover;
            color: white;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.8);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding-top: 70px;
            box-sizing: border-box;
            text-align: center;
        }

        .catalog {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding-top: 70px;
            box-sizing: border-box;
            text-align: center;
        }

        .btn {
            display: inline-block;
            padding: 15px 30px;
            background: #ff5722;
            color: white;
            text-decoration: none;
            font-size: 20px;
            margin-top: 20px;
            border-radius: 5px;
            transition: 0.3s;
        }

        .btn:hover {
            background: #e64a19;
        }

        .catalog,
        .product-page,
        .delivery {
            display: none;
        }

        .product {
            display: inline-block;
            width: 220px;
            margin: 15px;
            border: 1px solid #ddd;
            padding: 10px;
            text-align: center;
            background: #fff;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
        }

        .product img {
            width: 100%;
            border-radius: 5px;
        }

        .review {
            background: #f9f9f9;
            padding: 20px;
            margin: 10px;
            border-radius: 5px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            text-align: left;
        }

        footer {
            background: #333;
            color: white;
            padding: 10px;
            margin-top: 20px;
            width: 100%;
        }

        .product-page {
            margin-top: 80px;
            padding-top: 0;
        }

        .thank-you-message {
            font-size: 24px;
            color: green;
            font-weight: bold;
            margin-top: 30px;
        }
    </style>
</head>

<body>

    <header>
        <h1>Тазіки Shop_Тазіки для Олесі</h1>
        <nav>
            <ul>
                <li><a href="#" onclick="showSection('hero')">Головна</a></li>
                <li><a href="#" onclick="showSection('catalog')">Каталог</a></li>
                <li><a href="#" onclick="showSection('product-page')">Відгуки</a></li>
                <li><a href="#" onclick="showSection('order')">Оформити замовлення</a></li>
            </ul>
        </nav>
    </header>

    <!-- Головна сторінка -->
    <section id="hero" class="section hero">
        <h1>Купуйте найкращі тазіки для как і піпі!</h1>
        <p>Широкий вибір пластикових та металевих тазіків для каканя і пісяня.</p>
        <a href="#" class="btn" onclick="showSection('catalog')">Дивитись хуйню</a>
    </section>

    <!-- Каталог товарів -->
    <section id="catalog" class="section catalog">
        <h1>Наші тазіки</h1>

        <div class="product">
            <img src="https://images.prom.ua/6451559457_w400_h400_skladnoj-tazik-dlya.jpg" alt="Тазік 10л">
            <h3>Тазік 10л</h3>
            <p>Міцний пластиковий тазік.</p>
            <p class="price">150 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Тазік 10л')">Детальніше</a>
        </div>

        <div class="product">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQjkhWNa0mKlyIfnakh_aFzCjWSDfmMkBj2AA&s"
                alt="Тазік 20л">
            <h3>Тазік 20л</h3>
            <p>Великий тазік для господарських потреб.</p>
            <p class="price">250 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Тазік 20л')">Детальніше</a>
        </div>

        <div class="product">
            <img src="https://i.pinimg.com/564x/dc/13/6b/dc136b7a671c69cc9370458a6995b7db.jpg" alt="Не тазік 2гр">
            <h3>Не тазік 2гр</h3>
            <p>Діє дуже бистро і ефект ніби в очке єдинорога опинився</p>
            <p class="price">100000 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Не тазік 2гр')">Детальніше</a>
        </div>

        <div class="product">
            <img width=250 src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQLdGSw2vPS2WcYMqZgceeELSn9tpgOQNkjiANCzGQfEV280dN7HCnM-qQ_2kYmTOkk8zg&usqp=CAU" alt="Міні тазік 5л">
            <h3>Міні тазік 5л</h3>
            <p>Ідеальний для маленьких попок</p>
            <p class="price">350 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Міні тазік 5л')">Детальніше</a>
        </div>

        <div class="product">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRblD-moxXMANmAqRf9EnyQTXBIn8BUSrw3hw&s" alt="Літаючий тазік">
            <h3>Літаючий тазік</h3>
            <p>Літає до 2м </p>
            <p class="price">150 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Тазік 10л')">Детальніше</a>
        </div>

        <div class="product">
            <img src="https://images.prom.ua/5016907693_w200_h200_taz-20-l.jpg" alt="Тазік пластековий 20л">
            <h3>Тазік пластековий 20л</h3>
            <p>Універсальний тазік середнього розміру.</p>
            <p class="price">500 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Тазік пластековий 20л')">Детальніше</a>
        </div>

        <div class="product">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ8YKhVX_6EleUAPKIpgnRbNH4GABsrcG24mA&s" alt="Тазік з безкінечним дном">
            <h3>Тазік з безкінечним дном</h3>
            <p>цілий світ не заповнить тазіка говном</p>
            <p class="price">999999999999999999 грн</p>
            <a href="#" class="btn" onclick="goToOrder('Тазік з безкінечним дном')">Детальніше</a>
        </div>
    </section>
<!-- Відгуки -->
<section id="product-page" class="section product-page">
    <h2>Відгуки наших клієнтів</h2>
    <div class="review">
        <p class="author">Яйцеслав</p>
        <p>Тазік хуйня,я туда насрала,він проламався нахуй,всьо гімно на підлозі.Ставлю 1 пізду тому шо баба відпиздила
        </p>
    </div>
    <div class="review">
        <p class="author">Ядерний шептун</p>
        <p>Дуже хороший тазік,туда сцють пси,все подобаєтьсЯ</p>
    </div>
    <div class="review">
        <p class="author">Фараон</p>
        <p>Хуйня китайська 1 зірка фараона</p>
    </div>
    <div class="review">
        <p class="author">Амамут Рахал</p>
        <p>Як би можна було високо літати на ньому тоді було б 5 зірок а так 1</p>
    </div>
    <div class="review">
        <p class="author">Василь хуеносов</p>
        <p>Як на ньому переключати передачі влетів в стовб на великій скорості 3 зірки</p>
    </div>
    <div class="review">
        <p class="author">Джо Байден</p>
        <p>Барак Обама відправив нахуй на ньому 1 зірка</p>
    </div>
    <div class="review">
        <p class="author">Расист228</p>
        <p>Тазік хороший,до мене прийшли негри і стали моїми рабами 5 зірок</p>
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbJTEH1yFJuqwahJ7CKzZ9VXqYgbxSUAJXjg&s" width=200 alt="Тазік з безкінечним дном">
    </div>
    <div class="review">
        <p class="author">Яна Цист</p>
        <p>Все подобається,до мене ломляться мєнти в хату за масове вбивство 2 зірки</p>
    </div>
    <div class="review">
        <p class="author">Німець Олег</p>
        <p>Тазік норм відбивався ним від євреїв 4 зірки</p>
    </div>
    <div class="review">
        <p class="author">Тошенька</p>
        <p>Тазік сподобався 5 зірок</p>
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRHn1HKHVx8eYL1GEjPAHn4IBQq635w-qAsOg&s" width=250 alt="Тошенька">
    </div>
    <div class="review">
        <p class="author">Азам айталі</p>
        <p>З тазіком приїхав МГЕ братья 1зірка</p>
    </div>
    <div class="review">
        <p class="author">Андей довбойобов</p>
        <p>Замість тазікаприслали воєнком.1 зірка</p>
    </div>
    <div class="review">
        <p class="author">Аутист Андрій</p>
        <p>Тазик топ, 10/10 ,но якись Денні Эльфман з нього виліз и видалил мені роблокс 😭😭 1 зірок</p>
    </div>
    <div class="review">
        <p class="author">Бомжара34567</p>
        <p>Я покупала у них тазики,я в них живу 😍😍😍 5 зірок</p>
    </div>
    <a href="#" class="btn" onclick="showSection('catalog')">Повернутися до каталогу</a>
</section>

    <!-- Оформлення замовлення -->
    <section id="order" class="section">
        <h2>Оформити замовлення</h2>
        <form id="order-form" onsubmit="return showThankYouMessage()">
            <label for="name">Ім'я:</label><br>
            <input type="text" id="name" name="name" required><br><br>

            <label for="city">Місто:</label><br>
            <input type="text" id="city" name="city" required><br><br>

            <label for="oplata">Оплата:</label><br>
            <select id="oplata" name="oplata">
                <option value="Оплата картою">Оплата картою</option>
                <option value="Оплата натурою">Оплата натурою</option>
                <option value="Оплата картою">Оплата фоточками</option>
            </select><br><br>

            <label for="product">Товар:</label><br>
            <select id="product" name="product">
                <option value="Тазік 10л">Тазік 10л</option>
                <option value="Тазік 20л">Тазік 20л</option>
                <option value="Тазік квадратний 8л">Не тазік 2гр</option>
                <option value="Тазік овальний 30л">Міні тазік 5л</option>
                <option value="Тазік пластековий 20л">Тазік пластековий 20л</option>
                <option value="Тазік з безкінечним дном">Тазік з безкінечним дном</option>
                <option value="Тазік з безкінечним дном">Літаючий тазік</option>
            </select><br><br>

            <button type="submit" class="btn">Замовити</button>
        </form>

        <p id="thank-you-message" class="thank-you-message" style="display: none;">Дякуємо за покупку!
            скоро до тебе прийдуть спортики<3</p>
    </section>

    <footer>
        <p>&copy; 2025 Тазіки Shop. Всі дані передаються сторонім  особам.</p>
        <div>
            <h2>Розробники сайту</h2>
           <h4>Анна і Chat GPT,а також велике дякую Арсенові,що поміг виставити цей сайт на сервер </h4>
           <p>Рештам  дякую за ідеї,але ви не розробники тому я вас сюда не запишу!!!!</p>
           <h1>Сайт створений в честь Олесі</h1>
        </div>
    </footer>

    <script>
        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.style.display = 'none';
            });
            document.getElementById(sectionId).style.display = 'flex';
        }

        // Показати головну сторінку за замовчуванням
        document.addEventListener('DOMContentLoaded', () => {
            showSection('hero');
        });

        // Функція для переходу до замовлення з вибором товару
        function goToOrder(productName) {
            showSection('order');
            document.getElementById('product').value = productName;
        }

        // Функція для відображення повідомлення "Дякуємо за покупку"
        function showThankYouMessage() {
            event.preventDefault(); // Забороняє стандартну поведінку форми (відправка)
            document.getElementById('order-form').style.display = 'none'; // Приховує форму
            document.getElementById('thank-you-message').style.display = 'block'; // Показує повідомлення
        }
    </script>

</body>

</html>
