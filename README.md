<!DOCTYPE html>
<html lang="uk">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Загублений Шкарпеткослід 🧦</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #fce4ec;
            color: #333;
        }

        header {
            background-color: #ff4081;
            color: white;
            padding: 15px;
        }

        main {
            margin: 20px;
        }

        button {
            background-color: #ff4081;
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 5px;
        }

        button:hover {
            background-color: #e91e63;
        }

        #sock-list {
            list-style-type: none;
            padding: 0;
        }

        #sock-list li {
            background-color: white;
            margin: 10px auto;
            padding: 10px;
            border-radius: 5px;
            width: 50%;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
        }

        img {
            max-width: 100px;
            display: block;
            margin: 10px auto;
        }

        .reviews {
            margin-top: 10px;
            text-align: left;
            font-size: 14px;
        }
    </style>
</head>

<body>
    <header>
        <h1>Загублений Шкарпеткослід 🧦</h1>
        <p>Наймістичніше місце в інтернеті – база загублених шкарпеток!</p>
    </header>

    <main>
        <section id="upload-section">
            <h2>Додати загублену шкарпетку</h2>
            <input type="text" id="sock-owner" placeholder="Ваше ім'я">
            <input type="text" id="sock-name" placeholder="Назва шкарпетки">
            <input type="file" id="sock-image" accept="image/*">
            <button onclick="addSock()">🔍 Додати</button>
        </section>

        <section id="list-section">
            <h2>Зниклі шкарпетки</h2>
            <ul id="sock-list"></ul>
        </section>
    </main>

    <script>
        function loadSocks() {
            const sockList = document.getElementById("sock-list");
            sockList.innerHTML = "";

            const savedSocks = JSON.parse(localStorage.getItem("socks")) || [];

            savedSocks.forEach(sock => {
                addSockToDOM(sock);
            });
        }

        function addSock() {
            const ownerInput = document.getElementById("sock-owner");
            const nameInput = document.getElementById("sock-name");
            const fileInput = document.getElementById("sock-image");

            if (!ownerInput.value || !nameInput.value || !fileInput.files.length) {
                alert("Будь ласка, введіть ім'я, назву шкарпетки і виберіть фото!");
                return;
            }

            const file = fileInput.files[0];
            const reader = new FileReader();

            reader.onloadend = function () {
                const newSock = {
                    owner: ownerInput.value,
                    name: nameInput.value,
                    image: reader.result, // Збереження зображення у форматі Base64
                    reviews: []
                };

                const savedSocks = JSON.parse(localStorage.getItem("socks")) || [];
                savedSocks.push(newSock);
                localStorage.setItem("socks", JSON.stringify(savedSocks));

                addSockToDOM(newSock);

                ownerInput.value = "";
                nameInput.value = "";
                fileInput.value = "";
            };

            reader.readAsDataURL(file); // Перетворюємо зображення у Base64
        }

        function addSockToDOM(sock) {
            const sockList = document.getElementById("sock-list");
            const listItem = document.createElement("li");
            listItem.innerHTML = `<strong>${sock.name}</strong> (додав: ${sock.owner})<br>`;

            const img = document.createElement("img");
            img.src = sock.image;
            img.style.maxWidth = "100px";
            img.style.display = "block";
            img.style.margin = "10px auto";
            listItem.appendChild(img);

            const reviewButton = document.createElement("button");
            reviewButton.innerText = "💬 Залишити відгук";
            reviewButton.onclick = function () {
                leaveReview(sock, listItem);
            };
            listItem.appendChild(reviewButton);

            const reviewSection = document.createElement("div");
            reviewSection.classList.add("reviews");
            reviewSection.innerHTML = "<strong>Відгуки:</strong><ul class='review-list'></ul>";

            const reviewList = reviewSection.querySelector(".review-list");

            sock.reviews.forEach(review => {
                const reviewItem = document.createElement("li");
                reviewItem.innerText = review;
                reviewList.appendChild(reviewItem);
            });

            listItem.appendChild(reviewSection);
            sockList.appendChild(listItem);
        }

        function leaveReview(sock, sockItem) {
            const reviewText = prompt("Напишіть ваш відгук:");
            if (reviewText) {
                sock.reviews.push(reviewText);
                const savedSocks = JSON.parse(localStorage.getItem("socks")) || [];

                const updatedSocks = savedSocks.map(s => {
                    if (s.name === sock.name && s.owner === sock.owner) {
                        s.reviews = sock.reviews;
                    }
                    return s;
                });

                localStorage.setItem("socks", JSON.stringify(updatedSocks));

                const reviewList = sockItem.querySelector(".review-list");
                const reviewItem = document.createElement("li");
                reviewItem.innerText = reviewText;
                reviewList.appendChild(reviewItem);
            }
        }

        window.onload = loadSocks;
    </script>

</body>

</html>
