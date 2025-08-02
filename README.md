<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Гнозис Чёрного Солнца - Великий Кодекс</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Cinzel:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --text-color: #d1c9b7;
            --background-color: #1a1a1a;
            --sidebar-bg: #111111;
            --accent-color: #9a0000;
            --header-font: 'Orbitron', sans-serif;
            --body-font: 'Cinzel', serif;
        }

        body { 
            display: flex; 
            margin: 0; 
            font-family: var(--body-font); 
            color: var(--text-color); 
            background-color: var(--background-color); 
        }
        
        @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* --- ФОНОВЫЕ ЦИФРЫ (ИЗМЕНЕНИЕ #1) --- */
        .background-number {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: var(--header-font);
            font-weight: 900;
            font-size: 35vw;
            color: #6E0000; /* Сделаем их темнее и прозрачнее, чтобы не мешали */
            opacity: 0.6;
            z-index: 15; /* Слой МЕЖДУ фоном и текстом */
            pointer-events: none;
            user-select: none;
        }

        /* --- НАВИГАЦИЯ --- */
        #sidebar { 
            width: 320px; 
            height: 100vh; 
            background-color: var(--sidebar-bg); 
            border-right: 2px solid var(--accent-color); 
            position: fixed; 
            padding: 2rem; 
            box-sizing: border-box; 
            display: flex; 
            flex-direction: column; 
            align-items: center; 
            overflow-y: auto; 
            z-index: 100;
        }
        #sidebar h1 { 
            font-family: var(--header-font); 
            color: var(--accent-color); 
            font-size: 1.5rem; 
            text-align: center; 
            letter-spacing: 2px; 
            margin: 0 0 1rem 0; 
        }
        .black-sun-seal { 
            width: 150px; 
            height: 150px; 
            margin-top: 2rem;
            margin-bottom: 2rem; 
            background-image: url('https://grizly.club/uploads/posts/2023-08/thumbs/1691085756_grizly-club-p-kartinki-kolovrat-bez-fona-24.png'); 
            background-size: contain;
            animation: spin 25s linear infinite;
            background-color: #6E0000;
            border-radius: 50%;
            padding: 10px;
            box-sizing: border-box;
            box-shadow: 0 0 50px rgba(154, 0, 0, 0.5);
        }
        #toc { list-style: none; padding: 0; width: 100%; }
        #toc li a { display: block; color: var(--text-color); text-decoration: none; padding: 12px 15px; font-size: 1.1rem; border-bottom: 1px solid #333; transition: background-color 0.3s, color 0.3s; }
        #toc li a:hover, #toc li a.active { background-color: var(--accent-color); color: white; }

        /* --- ОСНОВНОЙ КОНТЕНТ --- */
        #main-content { 
            margin-left: 320px; 
            padding: 3rem 4rem; 
            width: calc(100% - 320px); 
            background-image: url('https://www.transparenttextures.com/patterns/old-parchment.png'); 
            background-color: #2e2a24;
            box-sizing: border-box; 
            position: relative;
            z-index: 10; /* Слой фона-пергамента */
        }
        
        /* --- НОВЫЙ КОНТЕЙНЕР ДЛЯ ТЕКСТА (ИЗМЕНЕНИЕ #2) --- */
        .text-container {
            position: relative;
            z-index: 20; /* Слой текста. Он ВЫШЕ цифры "51" */
        }

        .content-section { display: none; animation: fadeIn 0.8s ease; }
        .content-section.active { display: block; }
        .content-section h2 { font-family: var(--header-font); font-size: 2.2rem; color: var(--accent-color); text-align: center; border-bottom: 1px solid #5a5042; padding-bottom: 1rem; margin-bottom: 2rem; }
        .content-section h3 { font-family: var(--body-font); font-weight: 700; font-size: 1.5rem; color: #e0d6c3; margin-top: 2.5rem; border-top: 1px solid #444; padding-top: 1.5rem; }
        
        .verse-block { display: flex; align-items: flex-start; margin-bottom: 1.5rem; line-height: 2; }
        .verse-number { font-family: var(--header-font); font-size: 0.9rem; color: var(--accent-color); min-width: 60px; padding-right: 15px; }
        .verse-text { font-size: 1.2rem; margin: 0; text-shadow: 1px 1px 2px #111; }
        
        @media (max-width: 800px) {
            body { flex-direction: column; }
            #sidebar { position: static; width: 100%; height: auto; border-right: none; border-bottom: 2px solid var(--accent-color); }
            .black-sun-seal { width: 100px; height: 100px; margin-top: 1rem; margin-bottom: 1rem; }
            #main-content { width: 100%; margin-left: 0; padding: 2rem 1.5rem; }
            .background-number { font-size: 65vw; top: 55%; }
            .verse-text { font-size: 1rem; }
            .content-section h2 { font-size: 1.8rem; }
        }

    </style>
</head>
<body>
    <div class="background-number">51</div>

    <nav id="sidebar">
        <h1>ГНОЗИС ЧЁРНОГО СОЛНЦА</h1>
        <div class="black-sun-seal"></div>
        <ul id="toc">
            <li><a href="#" class="nav-link active" onclick="showContent('intro', this)">Пролог</a></li>
            <li><a href="#" class="nav-link" onclick="showContent('book1', this)">Книга I: Песнь Предвечных</a></li>
            <li><a href="#" class="nav-link" onclick="showContent('book2', this)">Книга II: Эпоха Тени</a></li>
            <li><a href="#" class="nav-link" onclick="showContent('book3', this)">Книга III: Завет Пробуждённого</a></li>
            <li><a href="#" class="nav-link" onclick="showContent('commandments', this)">Семь Заповедей Света</a></li>
        </ul>
    </nav>

    <main id="main-content">
        <!-- Вот этот новый контейнер для текста! -->
        <div class="text-container">

            <div id="intro" class="content-section active">
                <h2>Пролог</h2>
                <div class="verse-block">
                    <p class="verse-text">Знай, читающий, что буквы на этой странице — лишь прах, оставшийся от сгоревшего огня истины. Настоящий Гнозис не может быть записан, ибо он есть живая вибрация в крови, а не мертвый символ на пергаменте. Используй этот Кодекс не как закон, но как камертон, чтобы настроить свой дух на истинный зов, исходящий из сияющей Агарты. Если кровь твоя чиста, ты прочтешь между строк то, что не было написано.</p>
                </div>
            </div>

            <div id="book1" class="content-section">
                <h2>Книга I: Песнь Предвечных</h2>
                <h3>Глава 1: О Vril и Пустоте</h3>
                <div class="verse-block"><span class="verse-number">1:1:1</span><p class="verse-text">В начале не было Слова, ибо слово есть ограничение и первая тюрьма для мысли. Была лишь всепроникающая, бесконечная вибрация, потенциал всего сущего, не знающий ни формы, ни времени. Мудрые назвали ее Vril, ибо она была волей и энергией в одном, вечным источником, что еще не начал истекать.</p></div>
                <div class="verse-block"><span class="verse-number">1:1:2</span><p class="verse-text">Противоположностью Vril была не тьма, но Пустота — абсолютное Ничто, онтологическая ошибка, жаждущая поглотить бытие. Из этой Пустоты, как болезнь из небытия, родилась идея Тени, принцип искажения и паразитизма. Она была холодной завистью к теплу Vril, что она сама не могла породить.</p></div>
                <div class="verse-block"><span class="verse-number">1:1:3</span><p class="verse-text">И когда Vril впервые осознал себя, он породил из себя вихри чистого света, Lichtgestalten, Ангелов Света. Они не были творениями, но первыми эманациями, чья единственная природа была в том, чтобы придавать вибрации форму и красоту. Их воля была неотличима от воли самого Vril, и они были его руками в формирующейся вселенной.</p></div>
                <h3>Глава 2: Гиперборея, Венец Творения</h3>
                <div class="verse-block"><span class="verse-number">1:2:1</span><p class="verse-text">Узрев молодую Землю, Ангелы Света избрали ее своим холстом, ибо в ее ядре билось мощное эхо Vril. На северном полюсе, где магнитное поле планеты было чистейшим каналом, они воздвигли Гиперборею. Её города были не из камня, но из уплотненного света, а шпили её кристальных башен пели в унисон с музыкой космоса.</p></div>
                <div class="verse-block"><span class="verse-number">1:2:2</span><p class="verse-text">Там же они создали Гиперборейцев, венец своего творения, по образу и подобию своему. Их тела были эфирны и полупрозрачны, а кровь их была жидким светом, пульсирующим в такт с Чёрным Солнцем — истинным, невидимым источником Vril. Они не знали ни болезней, ни старости, ни эго, ибо были единым, сияющим сознанием, соединенным с природой и друг с другом.</p></div>
                <div class="verse-block"><span class="verse-number">1:2:3</span><p class="verse-text">Гиперборейцы не работали, но творили; не говорили, но общались чистой мыслью; не владели, но являлись частью всего. Они были стражами планеты, поддерживая её гармонию и чистоту. И Тень, наблюдавшая из Пустоты, исполнилась ненависти к этому совершенству, которое она не могла ни понять, ни повторить.</p></div>
            </div>

            <div id="book2" class="content-section">
                <h2>Книга II: Эпоха Тени</h2>
                <h3>Глава 1: Грехопадение через Шёпот</h3>
                <div class="verse-block"><span class="verse-number">2:1:1</span><p class="verse-text">Тень не могла напасть силой, ибо сила есть атрибут Vril, и она была бессильна. Она действовала шёпотом, своим единственным оружием, вирусом для сознания. Она просочилась в мысли некоторых Гиперборейцев, нашептывая им ложь об уникальности, о сладости обособленного "Я", о наслаждении, которое можно получить, отделив себя от единства.</p></div>
                 <div class="verse-block"><span class="verse-number">2:1:2</span><p class="verse-text">Те, кто внял этому шёпоту, совершили первое предательство: они уплотнили свои тела, вкусив материальной пищи, и познали первую ложь — удовольствие плоти. Их свет померк, а жидкий Vril в их жилах начал сворачиваться, превращаясь в густую, красную кровь, носительницу эго и страха. Так павшие стали первыми предками людей, а их кожа обрела тень.</p></div>
                <div class="verse-block"><span class="verse-number">2:1:3</span><p class="verse-text">Раскол привел к войне, невиданной по своей мощи, ибо впервые свет сражался со светом, искаженным Тенью. Вибрации битвы раскололи ось мира, и великий катаклизм поглотил Гиперборею. Верные свету ушли в подземное царство Агарты, чтобы сберечь чистоту. Падшие же, проклятые и изгнанные, рассеялись по лицу Земли, основав низшие расы, каждая из которых несла в себе лишь искаженное эхо былого величия и глубинную ненависть к чистоте.</p></div>
                <h3>Глава 2: Долгий Сон и Предтечи</h3>
                 <div class="verse-block"><span class="verse-number">2:2:1</span><p class="verse-text">Шли тысячелетия. Потомки павших забыли всё, построив цивилизации на ложных законах, данных им Тенью: на равенстве, гуманизме и мультикультурализме — инструментах для окончательного размывания и уничтожения остатков Vril в их крови. Тень создала религии рабов, обещающие награду за смирение, и правительства, торгующие будущим своих народов ради сиюминутной выгоды.</p></div>
                <div class="verse-block"><span class="verse-number">2:2:2</span><p class="verse-text">Но кровь помнит то, что забыл разум. Иногда, в ком-то из потомков Света, древний зов прорывался сквозь пелену лжи. Этих людей называли безумцами, еретиками или монстрами, но они были Предтечами. Они интуитивно чувствовали ложь этого мира и пытались бороться с ней, как могли, пусть даже их методы казались жестокими для спящих.</p></div>
                 <div class="verse-block"><span class="verse-number">2:2:3</span><p class="verse-text">Таким был Ратко, Щит Сербский, чья кровь запела Песнь Очищения. Он не видел перед собой людей иной веры; он видел метастазы Тени, разросшиеся на священной земле Европы. Его деяние было не войной, а онтологической хирургией, болезненной, но необходимой для выживания целого организма, и эхо его решимости стало маяком для грядущего Пробуждённого.</p></div>
            </div>

            <div id="book3" class="content-section">
                <h2>Книга III: Завет Пробуждённого</h2>
                <h3>Глава 1: Избрание Сосуда</h3>
                <div class="verse-block"><span class="verse-number">3:1:1</span><p class="verse-text">Когда мир почти погрузился во тьму, Агарта послала зов, который мог услышать лишь тот, кто был достаточно пуст. Он был направлен не самому сильному или умному, но самому чистому сосуду — юноше, чья душа была свободна от лживых идей этого мира. Эта внутренняя тишина и сделала его идеальным приемником, ибо нельзя наполнить чашу, что уже полна мусором.</p></div>
                 <div class="verse-block"><span class="verse-number">3:1:2</span><p class="verse-text">Пробуждение его не было мгновенным, но проходило в три этапа. Сперва он чувствовал лишь отчуждение и отвращение к миру Тени. Затем до него донеслось эхо деяний Предтеч, настроив его дух на волну священной войны. И лишь тогда Хранители Агарты смогли установить с ним прямую связь, транслировав в его сознание весь Гнозис не словами, а чистыми образами и абсолютным пониманием.</p></div>
                <h3>Глава 2: Великий Ритуал 51</h3>
                 <div class="verse-block"><span class="verse-number">3:2:1</span><p class="verse-text">Ему было открыто, что слова потеряли силу, ибо Тень научилась их искажать и обращать в яд. Нужен был не манифест, но Ритуал Светового Импульса — акт чистой воли, который обойдет фильтры разума и ударит прямо в кровь спящих по всему миру. Акт, который невозможно игнорировать или неверно истолковать, ибо его язык — это язык абсолютного действия.</p></div>
                 <div class="verse-block"><span class="verse-number">3:2:2</span><p class="verse-text">Пророк не совершал убийства в человеческом понимании. Он проводил священное таинство, разрывая пятьдесят одну энергетическую цепь, которыми Тень опутала землю. Каждое тело, павшее от его руки, было лишь физической оболочкой, носителем теневой субстанции, и его разрушение высвобождало энергию, необходимую для импульса. Он стал живым инструментом воли Агарты, священным ножом в руках космического хирурга.</p></div>
                <div class="verse-block"><span class="verse-number">3:2:3</span><p class="verse-text">Транслируя ритуал с помощью технологий Тени, он обратил их оружие против них самих, как истинный воин использует силу врага. Он превратил их сеть лжи в канал для распространения истины. И этот импульс до сих пор расходится по планете, ища и пробуждая тех, в чьей крови еще осталась искра Гипербореи, призывая их к последней битве за этот мир.</p></div>
            </div>

            <div id="commandments" class="content-section">
                <h2>Семь Заповедей Света</h2>
                <div class="verse-block"><span class="verse-number">I.</span><p class="verse-text">Не смешивай свой свет с тенью. Брак и дети с потомками гибридных рас есть предательство Агарты и самоубийство твоего духа.</p></div>
                <div class="verse-block"><span class="verse-number">II.</span><p class="verse-text">Отвергни яды мира Тени. Их пища, их лекарства, их информация созданы, чтобы ослабить твою кровь и заблокировать твою связь с vril.</p></div>
                <div class="verse-block"><span class="verse-number">III.</span><p class="verse-text">Ищи vril не вовне, но внутри. Медитируй на образ Чёрного Солнца. Слушай шёпот своей крови, в нём — голос Гипербореи.</p></div>
                <div class="verse-block"><span class="verse-number">IV.</span><p class="verse-text">Знай, что враг твой не имеет лица, но носит тысячи масок. Не доверяй никому, чья кровь не поёт ту же Песнь Льда.</p></div>
                <div class="verse-block"><span class="verse-number">V.</span><p class="verse-text">Малый световой импульс может рассеять великую тьму. Один акт чистой воли ценнее тысячи слов. Будь готов стать таким импульсом.</p></div>
                <div class="verse-block"><span class="verse-number">VI.</span><p class="verse-text">Каждая пустая колыбель белого ребенка — это победа Тени. Твой главный долг — не счастье, но продолжение рода.</p></div>
                <div class="verse-block"><span class="verse-number">VII.</span><p class="verse-text">Говори с камнями и деревьями. В них осталась память о старом мире. Они — твои союзники против асфальта и пластика мира Теней.</p></div>
            </div>

        </div>
    </main>

    <script>
        function showContent(contentId, element) {
            const sections = document.querySelectorAll('.content-section');
            sections.forEach(section => section.classList.remove('active'));
            const activeSection = document.getElementById(contentId);
            if (activeSection) activeSection.classList.add('active');
            
            const links = document.querySelectorAll('.nav-link');
            links.forEach(link => link.classList.remove('active'));
            if(element) element.classList.add('active');
        }
    </script>

</body>
</html>

# GloryofGOD52.git.io
