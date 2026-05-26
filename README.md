<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Во все тяжкие | Breaking Bad Universe</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0a0c10;
            font-family: 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
            color: #e0e0e0;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        /* кастомный скролл */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #1e1e1e;
        }
        ::-webkit-scrollbar-thumb {
            background: #3b9e3a;
            border-radius: 10px;
        }

        /* контейнер */
        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ========== ХЕДЕР ========== */
        .hero {
            position: relative;
            min-height: 85vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, rgba(0,0,0,0.85) 0%, rgba(30,40,20,0.7) 100%), 
                        url('https://avatars.mds.yandex.net/i?id=b39d4df9a28b5d7ff69bb21dd600f334ad235a9d-5257789-images-thumbs&n=13=80&w=2070&auto=format') center/cover no-repeat;
            background-blend-mode: overlay;
            border-bottom: 5px solid #3b9e3a;
        }

        .hero-content {
            max-width: 800px;
            padding: 20px;
            animation: fadeUp 0.9s ease-out;
        }

        .hero h1 {
            font-size: 4.5rem;
            font-weight: 800;
            letter-spacing: 4px;
            text-transform: uppercase;
            background: linear-gradient(135deg, #e9c46a, #e76f51);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
            margin-bottom: 20px;
        }

        .hero .tagline {
            font-size: 1.4rem;
            font-weight: 500;
            color: #cfe3cf;
            border-left: 4px solid #3b9e3a;
            padding-left: 20px;
            margin: 20px auto;
            max-width: 600px;
            font-style: italic;
        }

        .hero .badge {
            display: inline-block;
            background: #1f2a1b;
            padding: 8px 20px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.9rem;
            letter-spacing: 1px;
            color: #b1e0a2;
            margin-top: 20px;
            backdrop-filter: blur(4px);
        }

        @keyframes fadeUp {
            0% {
                opacity: 0;
                transform: translateY(30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ========== НАВИГАЦИЯ ========== */
        .sticky-nav {
            background: #0f1217f2;
            backdrop-filter: blur(12px);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid #2c3524;
        }

        .nav-links {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            padding: 1rem 0;
            flex-wrap: wrap;
        }

        .nav-links a {
            color: #dad7cd;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            font-size: 1.1rem;
            letter-spacing: 0.5px;
        }

        .nav-links a:hover {
            color: #7ed957;
            transform: translateY(-2px);
        }

        /* ========== ОБЩИЕ СЕКЦИИ ========== */
        section {
            padding: 70px 0;
            border-bottom: 1px solid #212529;
        }

        .section-title {
            font-size: 2.4rem;
            font-weight: 700;
            margin-bottom: 48px;
            text-align: center;
            position: relative;
            display: inline-block;
            width: 100%;
        }
        .section-title span {
            background: linear-gradient(120deg, #3b9e3a, #c2d600);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            border-bottom: 3px solid #3b9e3a;
            padding-bottom: 8px;
        }

        /* карточки персонажей */
        .characters-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 2rem;
            margin-top: 20px;
        }

        .character-card {
            background: #151a1f;
            border-radius: 28px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s;
            box-shadow: 0 8px 20px rgba(0,0,0,0.4);
            border: 1px solid #2d352e;
        }

        .character-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 30px rgba(0,0,0,0.5);
            border-color: #4c9e4a;
        }

        .character-img {
            height: 280px;
            background-size: cover;
            background-position: top center;
            position: relative;
        }

        .card-content {
            padding: 20px 20px 25px;
        }

        .card-content h3 {
            font-size: 1.8rem;
            margin-bottom: 8px;
            color: #f4a261;
        }

        .card-content p {
            color: #b9c0c6;
            font-size: 0.95rem;
        }

        /* cюжет */
        .plot-text {
            background: #0f1318e6;
            padding: 30px;
            border-radius: 32px;
            font-size: 1.12rem;
            line-height: 1.6;
            border-left: 6px solid #3b9e3a;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
        }

        .highlight {
            color: #e9c46a;
            font-weight: 600;
        }

        /* сезоны */
        .seasons-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            justify-content: center;
            margin: 30px 0 10px;
        }
        .season-badge {
            background: #1f2622;
            padding: 12px 28px;
            border-radius: 60px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.2s;
            border: 1px solid #3b9e3a50;
        }
        .season-badge strong {
            color: #e9c46a;
            font-size: 1.3rem;
        }
        .season-badge:hover {
            background: #2a352e;
            border-color: #7ed957;
            transform: scale(1.02);
        }

        /* цитаты */
        .quote-block {
            background: linear-gradient(145deg, #10151b, #0b0e12);
            border-radius: 48px;
            padding: 40px 30px;
            margin: 40px 0;
            text-align: center;
            box-shadow: 0 20px 30px -12px black;
        }
        .quote-text {
            font-size: 1.8rem;
            font-weight: 500;
            font-style: italic;
            color: #f5efdf;
            max-width: 850px;
            margin: 0 auto 20px;
        }
        .quote-author {
            font-size: 1.2rem;
            color: #b1bc9c;
            letter-spacing: 1px;
        }

        /* галерея кадров */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 22px;
            margin-top: 20px;
        }
        .gallery-item {
            border-radius: 24px;
            overflow: hidden;
            height: 220px;
            background-size: cover;
            background-position: center;
            transition: all 0.4s;
            filter: grayscale(0.2);
            border: 1px solid #2b332b;
        }
        .gallery-item:hover {
            transform: scale(1.02);
            filter: grayscale(0);
            border-color: #6ab04c;
            box-shadow: 0 10px 20px rgba(0,0,0,0.5);
        }

        /* факты */
        .facts-list {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: space-between;
        }
        .fact {
            flex: 1;
            min-width: 200px;
            background: #11161c;
            border-radius: 32px;
            padding: 25px 20px;
            text-align: center;
            border-bottom: 3px solid #3b9e3a;
        }
        .fact-number {
            font-size: 2.2rem;
            font-weight: 800;
            color: #e9c46a;
        }

        /* футер */
        footer {
            background: #05080c;
            padding: 40px 0 30px;
            text-align: center;
            color: #8d9b8a;
            font-size: 0.85rem;
            border-top: 1px solid #233022;
        }

        /* адаптив */
        @media (max-width: 780px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            .hero .tagline {
                font-size: 1rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .quote-text {
                font-size: 1.3rem;
            }
            .nav-links {
                gap: 1.2rem;
            }
        }
        @media (max-width: 480px) {
            .container {
                padding: 0 16px;
            }
            .character-img {
                height: 220px;
            }
        }

        /* кнопка вверх */
        .go-top {
            position: fixed;
            bottom: 30px;
            right: 20px;
            background: #2d6a2b;
            color: white;
            width: 46px;
            height: 46px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            text-decoration: none;
            opacity: 0.7;
            transition: 0.2s;
            z-index: 99;
            box-shadow: 0 4px 10px black;
        }
        .go-top:hover {
            opacity: 1;
            background: #54b435;
            transform: translateY(-3px);
        }
    </style>
</head>
<body>

    <!-- Герой / главный баннер -->
    <div class="hero">
        <div class="hero-content">
            <h1>ВО ВСЕ ТЯЖКИЕ</h1>
            <div class="tagline">«Химия -- это наука о превращениях»</div>
            <div class="badge">★ 5 сезонов • 62 эпизода ★</div>
        </div>
    </div>

    <!-- навигация (липкая) -->
    <div class="sticky-nav">
        <div class="container">
            <div class="nav-links">
                <a href="#about">Сюжет</a>
                <a href="#characters">Персонажи</a>
                <a href="#seasons">Сезоны</a>
                <a href="#gallery">Кадры</a>
                <a href="#facts">Факты</a>
            </div>
        </div>
    </div>

    <main>
        <div class="container">
            <!-- Сюжет -->
            <section id="about">
                <h2 class="section-title"><span>⚗️ История, изменившая телевидение</span></h2>
                <div class="plot-text">
                    <p>Скромный школьный учитель химии <span class="highlight">Уолтер Уайт</span> узнаёт, что болен раком лёгких. 
                    Желая обеспечить будущее своей семьи, он объединяется с бывшим учеником <span class="highlight">Джесси Пинкманом</span> 
                    и начинает варить метамфетамин высочайшей чистоты. Под псевдонимом <strong>«Хайзенберг»</strong> 
                    Уолтер погружается в мир наркокартелей, коррупции и насилия, постепенно превращаясь из тихого отца семейства 
                    в безжалостного криминального гения. История разворачивается в пустынях Нью-Мексико, затрагивая темы 
                    гордости, морального падения, искупления и последствий каждого выбора.</p>
                    <br>
                    <p>Сериал от <strong>Vince Gilligan</strong> получил более 260 наград, включая 16 премий «Эмми». 
                    <span class="highlight">«Во все тяжкие»</span> -- это мрачная, напряжённая и невероятно глубокая одиссея человека, который «постучался в дверь» и переступил черту.</p>
                </div>

                <!-- небольшая цитата в сюжете -->
                <div class="quote-block">
                    <div class="quote-text">«Я не в опасности, ШКИР. Я и есть опасность. Кто-то открывает дверь и получает пулю, а ты думаешь, что это я? Нет. Я тот, кто стучит!»</div>
                    <div class="quote-author">-- Уолтер Уайт (Хайзенберг)</div>
                </div>
            </section>

            <!-- Персонажи -->
            <section id="characters">
                <h2 class="section-title"><span>🧪 Главные герои</span></h2>
                <div class="characters-grid">
                    <div class="character-card">
                        <div class="character-img" style="background-image: url('https://avatars.mds.yandex.net/i?id=b5138ec1bacfc91410cfb1652f36bb36b72bbc15-10551030-images-thumbs&n=13'); background-size: cover; background-position: 50% 20%;"></div>
                        <div class="card-content">
                            <h3>Уолтер Уайт</h3>
                            <p>Гениальный химик, превратившийся в наркобарона Хайзенберга. Борется за семью, но теряет себя.</p>
                        </div>
                    </div>
                    <div class="character-card">
                        <div class="character-img" style="background-image: url('https://avatars.mds.yandex.net/i?id=6a4e61b22c836da4cbdf957cb51ba9e2e2310e38-10841731-images-thumbs&n=13'); background-size: cover; background-position: 50% 20%;"></div>
                        <div class="card-content">
                            <h3>Джесси Пинкман</h3>
                            <p>Бывший ученик Уолтера, мелкий дилер с добрым сердцем. Трагическая душа, мечущаяся между совестью и жестокостью.</p>
                        </div>
                    </div>
                    <div class="character-card">
                        <div class="character-img" style="background-image: url('https://avatars.mds.yandex.net/i?id=aee7bc25e63fbdced6336eec7ff46409a0aa1eeb-3713366-images-thumbs&n=13'); background-size: cover; background-position: 50% 20%;"></div>
                        <div class="card-content">
                            <h3>Скайлер Уайт</h3>
                            <p>Жена Уолтера, бухгалтер. Постепенно раскрывает тёмную сторону мужа и пытается защитить детей.</p>
                        </div>
                    </div>
                    <div class="character-card">
                        <div class="character-img" style="background-image: url('https://avatars.mds.yandex.net/i?id=2769a698c09f08910d796ab9ac762c67a384d2e1-5448346-images-thumbs&n=13'); background-size: cover; background-position: 50% 20%;"></div>
                        <div class="card-content">
                            <h3>Хэнк Шрейдер</h3>
                            <p>Агент DEA, свояк Уолтера. Одержим охотой на Хайзенберга, не подозревая, кто скрывается за маской.</p>
                        </div>
                    </div>
                    <div class="character-card">
                        <div class="character-img" style="background-image: url('https://avatars.mds.yandex.net/i?id=0df98d953f7baec83d65499c830f83f61a4200fc-8497159-images-thumbs&n=13'); background-size: cover; background-position: 50% 20%;"></div>
                        <div class="card-content">
                            <h3>Сол Гудман</h3>
                            <p>Колоритный адвокат преступников. «Лучший в своём деле» с рекламой «Позвоните Солу!».</p>
                        </div>
                    </div>
                    <div class="character-card">
                        <div class="character-img" style="background-image: url('https://avatars.mds.yandex.net/i?id=7243222238ad36e437f4ef2c2c66c3b2710dd58f-4421718-images-thumbs&n=13'); background-size: cover; background-position: 50% 20%;"></div>
                        <div class="card-content">
                            <h3>Майк Эрмантраут</h3>
                            <p>Бывший полицейский, чистильщик и телохранитель Гуса Фринга. Холоден, профессионален и принципиален.</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Сезоны -->
            <section id="seasons">
                <h2 class="section-title"><span>📺 Сезоны и рейтинг</span></h2>
                <div class="seasons-grid">
                    <div class="season-badge"><strong>1 сезон</strong> -- 7 эпизодов</div>
                    <div class="season-badge"><strong>2 сезон</strong> -- 13 эпизодов</div>
                    <div class="season-badge"><strong>3 сезон</strong> -- 13 эпизодов</div>
                    <div class="season-badge"><strong>4 сезон</strong> -- 13 эпизодов</div>
                    <div class="season-badge"><strong>5 сезон</strong> -- 16 эпизодов (финал)</div>
                </div>
                <div style="text-align: center; margin: 30px 0 0; background:#10151b; border-radius: 40px; padding: 16px;">
                    <p>⭐ Рейтинг IMDb: <strong style="color: #f4a261; font-size: 1.6rem;">9.5/10</strong> -- занимает место в топ-3 лучших сериалов всех времён 🏆</p>
                    <p style="font-size:0.9rem;">"Лучший финал в истории телевидения" -- The New York Times</p>
                </div>
            </section>

            <!-- Галерея (кадры из сериала) -->
            <section id="gallery">
                <h2 class="section-title"><span>🎬 Культовые кадры</span></h2>
                <div class="gallery">
                    <div class="gallery-item" style="background-image: url('https://avatars.mds.yandex.net/i?id=fbfc89a92b73d24a0d74824e12cb022475c5a8f6-8392873-images-thumbs&n=13=80&w=1974&auto=format');"></div>
                    <div class="gallery-item" style="background-image: url('https://avatars.mds.yandex.net/i?id=53e783eed5e74c542c0bfc4bd590ec12d03a92a4-7759147-images-thumbs&n=13=80&w=1974&auto=format');"></div>
                    <div class="gallery-item" style="background-image: url('https://avatars.mds.yandex.net/i?id=d2e4907412afc17ef4a01bea2eacf1824d99608f-5760153-images-thumbs&n=13=80&w=1974&auto=format');"></div>
                    <div class="gallery-item" style="background-image: url('https://avatars.mds.yandex.net/i?id=4f2c0c64fddc8f498eb40bd050aeee47acd47381-4969887-images-thumbs&n=1380&w=1974&auto=format');"></div>
                </div>
                <p style="text-align:center; margin-top:20px; font-size:0.85rem; opacity:0.7;">Атмосфера пустыни, химических лабораторий и напряжения -- визитная карточка сериала.</p>
            </section>

            <!-- Интересные факты -->
            <section id="facts">
                <h2 class="section-title"><span>⚡ Грязная химия: факты</span></h2>
                <div class="facts-list">
                    <div class="fact">
                        <div class="fact-number">#1</div>
                        <p>Брайан Крэнстон (Уолтер) сам предложил идею носить шляпу, чтобы создать образ Хайзенберга.</p>
                    </div>
                    <div class="fact">
                        <div class="fact-number">#2</div>
                        <p>Сцена с пиццей на крыше была снята с первого дубля. Крэнстон идеально бросил пиццу, и её оставили в сериале.</p>
                    </div>
                    <div class="fact">
                        <div class="fact-number">#3</div>
                        <p>Гус Фринг (Джанкарло Эспозито) настоял, чтобы его персонаж был максимально сдержанным и холодным.</p>
                    </div>
                    <div class="fact">
                        <div class="fact-number">#4</div>
                        <p>Фильм «Путь: Во все тяжкие» (El Camino) завершает историю Джесси Пинкмана.</p>
                    </div>
                </div>
            </section>

            <!-- дополнительный блок о приквеле -->
            <div style="background: radial-gradient(circle at 10% 30%, #111a18, #030507); border-radius: 38px; padding: 35px 25px; margin: 20px 0 60px; text-align: center;">
                <h3 style="font-size: 1.9rem; color:#c6d166;">🌵 Лучше звоните Солу</h3>
                <p style="max-width: 700px; margin: 20px auto;">Приквел «Во все тяжкие» рассказывает о приключениях Сола Гудмана (Джимми Макгилла) и Майка Эрмантраута. Не менее культовый сериал, расширяющий вселенную.</p>
                <span style="display: inline-block; background:#2a5836; padding: 8px 22px; border-radius: 50px; font-weight: 600;">⭐⭐⭐⭐⭐ 9.0 IMDb</span>
            </div>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>© 2026 | Сайт создан поклонниками сериала «Во все тяжкие» (Breaking Bad).</p>
            <p style="margin-top: 12px;">Все права на изображения и персонажей принадлежат AMC, Sony Pictures Television.</p>
            <p style="margin-top: 8px;">«Say my name. -- Heisenberg. -- You're goddamn right.»</p>
        </div>
    </footer>

    <!-- кнопка наверх -->
    <a href="#" class="go-top" aria-label="Наверх">↑</a>

</body>
</html>
