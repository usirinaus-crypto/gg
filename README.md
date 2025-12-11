<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сердечки за любовные фразы</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            color: #333;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            padding: 30px;
            margin-top: 20px;
            text-align: center;
            position: relative;
            z-index: 10;
        }
        
        h1 {
            color: #e91e63;
            margin-bottom: 15px;
            font-size: 2.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .subtitle {
            color: #666;
            font-size: 1.2rem;
            margin-bottom: 30px;
            line-height: 1.5;
        }
        
        .input-container {
            margin: 30px 0;
            position: relative;
        }
        
        textarea {
            width: 100%;
            height: 150px;
            padding: 20px;
            border-radius: 15px;
            border: 2px solid #ffb6c1;
            font-size: 1.1rem;
            resize: none;
            outline: none;
            transition: all 0.3s;
            box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.05);
        }
        
        textarea:focus {
            border-color: #e91e63;
            box-shadow: 0 0 0 3px rgba(233, 30, 99, 0.1);
        }
        
        .hint {
            color: #777;
            font-size: 0.9rem;
            margin-top: 10px;
            text-align: left;
        }
        
        .heart-counter {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
            font-size: 1.3rem;
            color: #e91e63;
            font-weight: bold;
        }
        
        .heart-counter i {
            margin-right: 10px;
            font-size: 1.8rem;
            animation: pulse 1.5s infinite;
        }
        
        .phrases {
            background-color: #fff5f7;
            border-radius: 15px;
            padding: 20px;
            margin-top: 30px;
            border-left: 5px solid #e91e63;
            text-align: left;
        }
        
        .phrases h3 {
            color: #e91e63;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }
        
        .phrases h3 i {
            margin-right: 10px;
        }
        
        .phrases ul {
            list-style-type: none;
            padding-left: 10px;
        }
        
        .phrases li {
            padding: 8px 0;
            border-bottom: 1px dashed #ffcdd2;
            color: #555;
        }
        
        .phrases li:last-child {
            border-bottom: none;
        }
        
        .phrases li i {
            color: #e91e63;
            margin-right: 10px;
        }
        
        .footer {
            margin-top: 30px;
            color: #777;
            font-size: 0.9rem;
            text-align: center;
        }
        
        /* Анимация сердечек */
        .heart {
            position: fixed;
            font-size: 24px;
            color: #e91e63;
            pointer-events: none;
            z-index: 1;
            opacity: 0;
            animation: floatUp 4s linear forwards;
        }
        
        @keyframes floatUp {
            0% {
                opacity: 1;
                transform: translateY(0) rotate(0deg);
            }
            100% {
                opacity: 0;
                transform: translateY(-100vh) rotate(360deg);
            }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        /* Адаптивность */
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            textarea {
                height: 120px;
            }
        }
        
        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .container {
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1><i class="fas fa-heart"></i> Сайт любовных сердечек</h1>
        <p class="subtitle">Напишите в поле ниже любую фразу о любви, и вы получите красивые анимированные сердечки! Попробуйте "Я люблю тебя" или другие варианты из списка ниже.</p>
        
        <div class="heart-counter">
            <i class="fas fa-heart"></i>
            <span id="counter">0</span> сердечек создано
        </div>
        
        <div class="input-container">
            <textarea id="loveInput" placeholder="Напишите здесь ваше признание..."></textarea>
            <p class="hint">Совет: чем длиннее фраза, тем больше сердечек появится!</p>
        </div>
        
        <div class="phrases">
            <h3><i class="fas fa-lightbulb"></i> Попробуйте эти фразы:</h3>
            <ul>
                <li><i class="fas fa-heart"></i> Я люблю тебя</li>
                <li><i class="fas fa-heart"></i> Люблю тебя</li>
                <li><i class="fas fa-heart"></i> I love you</li>
                <li><i class="fas fa-heart"></i> Ты мне нравишься</li>
                <li><i class="fas fa-heart"></i> Обожаю тебя</li>
                <li><i class="fas fa-heart"></i> Я тебя обожаю</li>
                <li><i class="fas fa-heart"></i> Ты моя любовь</li>
                <li><i class="fas fa-heart"></i> Моя любовь</li>
            </ul>
        </div>
        
        <div class="footer">
            <p>Сделано с <i class="fas fa-heart" style="color:#e91e63;"></i> для всех влюблённых</p>
            <p>Сердечки будут появляться при вводе любых фраз, содержащих слова о любви</p>
        </div>
    </div>

    <script>
        const loveInput = document.getElementById('loveInput');
        const counter = document.getElementById('counter');
        let heartCount = 0;
        
        // Фразы, которые будут активировать сердечки
        const lovePhrases = [
            'люблю', 'обожаю', 'нравишься', 'love', 'adore', 'like', 
            'милый', 'милая', 'дорогой', 'дорогая', 'сердце', 'любовь'
        ];
        
        // Слова, которые могут быть частью фразы "я люблю тебя"
        const lovePatterns = [
            'я люблю тебя', 'люблю тебя', 'i love you', 'love you', 
            'ты мне нравишься', 'я тебя обожаю', 'обожаю тебя',
            'ты моя любовь', 'моя любовь', 'любимый', 'любимая'
        ];
        
        loveInput.addEventListener('input', function() {
            const text = this.value.toLowerCase().trim();
            
            // Проверяем, содержит ли текст любую из фраз о любви
            const hasLovePhrase = lovePhrases.some(phrase => text.includes(phrase));
            
            if (hasLovePhrase && text.length > 0) {
                // Определяем, насколько много сердечек создать
                let heartQuantity = Math.min(Math.floor(text.length / 5), 20);
                
                // Если обнаружена точная фраза "я люблю тебя" или подобная, создаем больше сердечек
                const hasExactLovePhrase = lovePatterns.some(pattern => text.includes(pattern));
                if (hasExactLovePhrase) {
                    heartQuantity = Math.min(Math.floor(text.length / 3), 30);
                }
                
                // Создаем сердечки
                createHearts(heartQuantity);
                
                // Обновляем счетчик
                heartCount += heartQuantity;
                counter.textContent = heartCount;
                
                // Если введена точная фраза "я люблю тебя", добавляем особый эффект
                if (text.includes('я люблю тебя') || text.includes('люблю тебя')) {
                    createSpecialHearts();
                }
            }
        });
        
        function createHearts(quantity) {
            for (let i = 0; i < quantity; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.innerHTML = '<i class="fas fa-heart"></i>';
                    heart.classList.add('heart');
                    
                    // Случайная позиция по горизонтали
                    const leftPos = Math.random() * 100;
                    heart.style.left = leftPos + 'vw';
                    
                    // Случайный размер
                    const size = Math.random() * 30 + 20;
                    heart.style.fontSize = size + 'px';
                    
                    // Случайный цвет (оттенки красного/розового)
                    const hue = Math.floor(Math.random() * 20 + 330);
                    heart.style.color = `hsl(${hue}, 90%, 60%)`;
                    
                    // Случайная задержка анимации
                    const animationDuration = Math.random() * 3 + 3;
                    heart.style.animationDuration = animationDuration + 's';
                    
                    document.body.appendChild(heart);
                    
                    // Удаляем сердечко после завершения анимации
                    setTimeout(() => {
                        heart.remove();
                    }, animationDuration * 1000);
                }, i * 100);
            }
        }
        
        function createSpecialHearts() {
            // Создаем несколько больших сердечек для особого эффекта
            for (let i = 0; i < 5; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.innerHTML = '<i class="fas fa-heart"></i>';
                    heart.classList.add('heart');
                    
                    const leftPos = Math.random() * 80 + 10;
                    heart.style.left = leftPos + 'vw';
                    
                    heart.style.fontSize = '50px';
                    heart.style.color = '#e91e63';
                    heart.style.zIndex = '5';
                    
                    heart.style.animationDuration = '4s';
                    
                    document.body.appendChild(heart);
                    
                    setTimeout(() => {
                        heart.remove();
                    }, 4000);
                }, i * 200);
            }
        }
        
        // Добавляем начальные сердечки для демонстрации
        window.addEventListener('load', () => {
            setTimeout(() => {
                createHearts(5);
                heartCount = 5;
                counter.textContent = heartCount;
            }, 1000);
        });
    </script>
</body>
</html>
