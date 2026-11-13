<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Isi Piringku Challenge</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: 'Trebuchet MS', sans-serif;
    background: #fff8e9;
    color: #344638;
    text-align: center;
}

header {
    background: #75a96b;
    color: white;
    padding: 25px 15px;
}

header h1 {
    margin: 0;
    font-size: 30px;
}

.container {
    max-width: 950px;
    margin: auto;
    padding: 20px;
}

h2 {
    color: #527d4e;
}

.instructions {
    background: #e8f2df;
    padding: 15px;
    border-radius: 15px;
    margin-bottom: 20px;
    line-height: 1.6;
}

.plate {
    width: 340px;
    height: 340px;
    margin: 20px auto;
    border: 12px solid #d7d7d7;
    border-radius: 50%;
    background: white;
    overflow: hidden;
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-template-rows: 1fr 1fr;
    box-shadow: 0 5px 15px #0002;
}

.zone {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 8px;
    border: 2px dashed #ffffffaa;
    min-width: 0;
    transition: 0.2s;
}

.zone h3 {
    font-size: 14px;
    margin: 3px;
}

.zone small {
    font-size: 12px;
}

.vegetable {
    background: #b8d99e;
    grid-column: 1;
    grid-row: 1;
}

.staple {
    background: #f4d58d;
    grid-column: 1;
    grid-row: 2;
}

.fruit {
    background: #f5b8a5;
    grid-column: 2;
    grid-row: 1;
}

.protein {
    background: #a9c9e5;
    grid-column: 2;
    grid-row: 2;
}

.zone.hover {
    outline: 3px solid #527d4e;
}

.zone-items {
    font-size: 12px;
    margin-top: 5px;
    word-break: break-word;
}

.food-list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 12px;
    margin: 20px 0;
}

.food {
    background: white;
    border: 2px solid #e5e5e5;
    border-radius: 13px;
    padding: 12px;
    width: 105px;
    cursor: grab;
    font-size: 15px;
    box-shadow: 0 3px 6px #0001;
    transition: 0.2s;
    touch-action: none;
    user-select: none;
}

.food:hover {
    transform: translateY(-4px);
    border-color: #75a96b;
}

.food.dragging {
    opacity: 0.5;
}

.food span {
    display: block;
    font-size: 30px;
    margin-bottom: 5px;
}

.food.used {
    opacity: 0.3;
    cursor: default;
}

button {
    background: #75a96b;
    color: white;
    border: none;
    padding: 12px 24px;
    border-radius: 10px;
    font-size: 15px;
    cursor: pointer;
    margin: 8px;
}

button:hover {
    background: #527d4e;
}

#feedback {
    font-weight: bold;
    margin: 15px;
    min-height: 25px;
}

.score {
    font-size: 18px;
    font-weight: bold;
    color: #527d4e;
}

@media(max-width: 450px) {
    .plate {
        width: 310px;
        height: 310px;
    }

    header h1 {
        font-size: 24px;
    }
}
</style>
</head>

<body>

<header>
    <h1>🥗 Isi Piringku Challenge!</h1>
    <p>Upgrade Your Plate, Upgrade Your Health!</p>
</header>

<div class="container">

    <div class="instructions">
        <h2>How to Play?</h2>
        <p>
            Yuk, susun makanan bergizi ke dalam piring!
            Drag setiap makanan ke bagian yang sesuai
            dengan panduan Isi Piringku.
        </p>
    </div>

    <h2>🍽️ Susun Piringmu!</h2>

    <div class="plate">

        <div class="zone vegetable" data-category="vegetable">
            <h3>🥦 SAYURAN</h3>
            <small>⅓ bagian</small>
            <div class="zone-items"></div>
        </div>

        <div class="zone fruit" data-category="fruit">
            <h3>🍎 BUAH</h3>
            <small>⅙ bagian</small>
            <div class="zone-items"></div>
        </div>

        <div class="zone staple" data-category="staple">
            <h3>🍚 MAKANAN POKOK</h3>
            <small>⅓ bagian</small>
            <div class="zone-items"></div>
        </div>

        <div class="zone protein" data-category="protein">
            <h3>🍗 LAUK-PAUK</h3>
            <small>⅙ bagian</small>
            <div class="zone-items"></div>
        </div>

    </div>

    <h2>Pilih Makananmu!</h2>
    <p>Geser makanan ke kategori yang tepat.</p>

    <div class="food-list" id="foodList">

        <div class="food" draggable="true" data-category="staple">
            <span>🍚</span>Nasi
        </div>

        <div class="food" draggable="true" data-category="staple">
            <span>🥔</span>Kentang
        </div>

        <div class="food" draggable="true" data-category="staple">
            <span>🌽</span>Jagung
        </div>

        <div class="food" draggable="true" data-category="vegetable">
            <span>🥦</span>Brokoli
        </div>

        <div class="food" draggable="true" data-category="vegetable">
            <span>🥕</span>Wortel
        </div>

        <div class="food" draggable="true" data-category="vegetable">
            <span>🥬</span>Bayam
        </div>

        <div class="food" draggable="true" data-category="protein">
            <span>🍗</span>Ayam
        </div>

        <div class="food" draggable="true" data-category="protein">
            <span>🐟</span>Ikan
        </div>

        <div class="food" draggable="true" data-category="protein">
            <span>🥚</span>Telur
        </div>

        <div class="food" draggable="true" data-category="fruit">
            <span>🍎</span>Apel
        </div>

        <div class="food" draggable="true" data-category="fruit">
            <span>🍌</span>Pisang
        </div>

        <div class="food" draggable="true" data-category="fruit">
            <span>🍊</span>Jeruk
        </div>

    </div>

    <div class="score">
        Skor: <span id="score">0</span> / 12
    </div>

    <div id="feedback"></div>

    <button onclick="checkResult()">Periksa Jawaban</button>
    <button onclick="resetGame()">Ulangi Permainan</button>

</div>

<script>

let score = 0;
let draggedItem = null;

const foods = document.querySelectorAll(".food");
const zones = document.querySelectorAll(".zone");

foods.forEach(food => {

    food.addEventListener("dragstart", () => {
        if (food.classList.contains("used")) return;
        draggedItem = food;
        food.classList.add("dragging");
    });

    food.addEventListener("dragend", () => {
        food.classList.remove("dragging");
    });

    food.addEventListener("touchstart", () => {
        if (food.classList.contains("used")) return;
        draggedItem = food;
        food.classList.add("dragging");
    }, {passive: true});

    food.addEventListener("touchend", e => {
        if (!draggedItem) return;

        const touch = e.changedTouches[0];
        const target = document.elementFromPoint(
            touch.clientX,
            touch.clientY
        );

        const zone = target?.closest(".zone");

        if (zone) placeFood(zone);

        food.classList.remove("dragging");
        draggedItem = null;
    });
});

zones.forEach(zone => {

    zone.addEventListener("dragover", e => {
        e.preventDefault();
        zone.classList.add("hover");
    });

    zone.addEventListener("dragleave", () => {
        zone.classList.remove("hover");
    });

    zone.addEventListener("drop", e => {
        e.preventDefault();
        zone.classList.remove("hover");

        if (draggedItem) placeFood(zone);
    });

});

function placeFood(zone) {

    if (!draggedItem) return;

    const correct = draggedItem.dataset.category;
    const target = zone.dataset.category;

    if (correct === target) {

        const item = document.createElement("span");

        item.textContent =
            draggedItem.querySelector("span").textContent +
            " " + draggedItem.textContent.trim();

        zone.querySelector(".zone-items").appendChild(item);

        draggedItem.classList.add("used");

        score++;

        document.getElementById("score").textContent = score;

        document.getElementById("feedback").textContent =
            "Benar! Makanan berhasil ditempatkan! 🎉";

        if (score === 12) {
            document.getElementById("feedback").textContent =
                "Hebat! Semua makanan berhasil disusun! 🥗";
        }

    } else {

        document.getElementById("feedback").textContent =
            "Ups! Coba tempatkan di kategori yang lain. 😊";

    }

    draggedItem = null;
}

function checkResult() {

    if (score === 12) {
        document.getElementById("feedback").textContent =
            "🏆 PERFECT! Kamu berhasil menyusun seluruh Isi Piringku!";
    } else {
        document.getElementById("feedback").textContent =
            "Masih ada " + (12 - score) +
            " makanan yang belum ditempatkan. Semangat!";
    }

}

function resetGame() {

    score = 0;
    draggedItem = null;

    document.getElementById("score").textContent = 0;
    document.getElementById("feedback").textContent = "";

    foods.forEach(food => {
        food.classList.remove("used");
    });

    document.querySelectorAll(".zone-items").forEach(zone => {
        zone.innerHTML = "";
    });

}

</script>

</body>
</html>
