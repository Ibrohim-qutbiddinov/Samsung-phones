<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>S21 Seriyasi Katalogi</title>
    <style>
        :root { --samsung-blue: #034ea2; --bg: #0f172a; --card: #1e293b; }
        body { font-family: 'Segoe UI', sans-serif; background: var(--bg); color: white; margin: 0; padding: 20px; }
        .container { max-width: 1100px; margin: auto; }
        header { text-align: center; padding: 30px; border-bottom: 2px solid var(--samsung-blue); margin-bottom: 30px; }
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; }
        .card { background: var(--card); border-radius: 20px; padding: 20px; text-align: center; border: 1px solid #334155; }
        .phone-img { width: 100%; max-width: 200px; height: 250px; object-fit: contain; margin-bottom: 15px; }
        
        .section-title { font-size: 0.8rem; color: #94a3b8; margin: 15px 0 8px; text-transform: uppercase; letter-spacing: 1px; }
        .btn-group { display: flex; justify-content: center; gap: 8px; flex-wrap: wrap; }
        
        button { background: #334155; border: none; color: white; padding: 8px 12px; border-radius: 6px; cursor: pointer; transition: 0.2s; }
        button.active { background: var(--samsung-blue); font-weight: bold; }
        
        .color-dot { width: 25px; height: 25px; border-radius: 50%; border: 2px solid #fff; cursor: pointer; transition: 0.3s; }
        .color-dot.active { transform: scale(1.3); border-color: #38bdf8; }

        .specs-box { margin-top: 20px; padding: 15px; background: #0f172a; border-radius: 12px; color: #38bdf8; font-family: monospace; font-size: 0.9rem; }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>Samsung Galaxy S21 Seriyasi</h1>
        <p>Modelni tanlang va xususiyatlarini ko'ring</p>
    </header>

    <div class="grid">
        <div class="card" id="s21">
            <img src="https://images.samsung.com/is/image/samsung/p6pim/uz_uz/galaxy-s21/gallery/uz-uz-galaxy-s21-5g-g991-sm-g991bzagskz-368324835" class="phone-img" id="img-s21">
            <h3>Galaxy S21 5G</h3>
            
            <div class="section-title">Ranglar</div>
            <div class="btn-group">
                <div class="color-dot active" style="background: #6b6d70;" onclick="changeColor('s21', 'Gray', this)"></div>
                <div class="color-dot" style="background: #7b68ee;" onclick="changeColor('s21', 'Violet', this)"></div>
                <div class="color-dot" style="background: #fff;" onclick="changeColor('s21', 'White', this)"></div>
            </div>

            <div class="section-title">Xotira</div>
            <div class="btn-group">
                <button class="active" onclick="changeSpecs('s21', '128GB', '8GB', this)">128GB</button>
                <button onclick="changeSpecs('s21', '256GB', '8GB', this)">256GB</button>
            </div>

            <div class="specs-box" id="info-s21">Rang: Gray | RAM: 8GB | Xotira: 128GB</div>
        </div>

        <div class="card" id="s21p">
            <img src="https://images.samsung.com/is/image/samsung/p6pim/uz_uz/2101/gallery/uz-uz-galaxy-s21-plus-5g-g996-sm-g996bzkaskz-368325752" class="phone-img" id="img-s21p">
            <h3>Galaxy S21+ 5G</h3>
            
            <div class="section-title">Ranglar</div>
            <div class="btn-group">
                <div class="color-dot active" style="background: #111;" onclick="changeColor('s21p', 'Black', this)"></div>
                <div class="color-dot" style="background: #c0c0c0;" onclick="changeColor('s21p', 'Silver', this)"></div>
                <div class="color-dot" style="background: #7b68ee;" onclick="changeColor('s21p', 'Violet', this)"></div>
            </div>

            <div class="section-title">Xotira</div>
            <div class="btn-group">
                <button class="active" onclick="changeSpecs('s21p', '128GB', '8GB', this)">128GB</button>
                <button onclick="changeSpecs('s21p', '256GB', '8GB', this)">256GB</button>
            </div>

            <div class="specs-box" id="info-s21p">Rang: Black | RAM: 8GB | Xotira: 128GB</div>
        </div>

        <div class="card" id="s21u" style="border-color: #ffd700;">
            <img src="https://images.samsung.com/is/image/samsung/p6pim/uz_uz/2101/gallery/uz-uz-galaxy-s21-ultra-5g-g998-sm-g998bzkgskz-368326233" class="phone-img" id="img-s21u">
            <h3>Galaxy S21 Ultra 5G</h3>
            
            <div class="section-title">Ranglar</div>
            <div class="btn-group">
                <div class="color-dot active" style="background: #111;" onclick="changeColor('s21u', 'Black', this)"></div>
                <div class="color-dot" style="background: #c0c0c0;" onclick="changeColor('s21u', 'Silver', this)"></div>
            </div>

            <div class="section-title">Xotira</div>
            <div class="btn-group">
                <button class="active" onclick="changeSpecs('s21u', '128GB', '12GB', this)">128GB</button>
                <button onclick="changeSpecs('s21u', '256GB', '12GB', this)">256GB</button>
                <button onclick="changeSpecs('s21u', '512GB', '16GB', this)">512GB</button>
            </div>

            <div class="specs-box" id="info-s21u">Rang: Black | RAM: 12GB | Xotira: 128GB</div>
        </div>
    </div>
</div>

<script>
    function changeColor(modelId, colorName, element) {
        // Dotlarni yangilash
        const dots = element.parentElement.querySelectorAll('.color-dot');
        dots.forEach(d => d.classList.remove('active'));
        element.classList.add('active');

        // Ma'lumotni yangilash
        const info = document.getElementById('info-' + modelId);
        const parts = info.innerText.split('|');
        info.innerText = `Rang: ${colorName} |${parts[1]}|${parts[2]}`;
    }

    function changeSpecs(modelId, storage, ram, element) {
        // Tugmalarni yangilash
        const btns = element.parentElement.querySelectorAll('button');
        btns.forEach(b => b.classList.remove('active'));
        element.classList.add('active');

        // Ma'lumotni yangilash
        const info = document.getElementById('info-' + modelId);
        const parts = info.innerText.split('|');
        info.innerText = `${parts[0]} | RAM: ${ram} | Xotira: ${storage}`;
    }
</script>

</body>
</html>
