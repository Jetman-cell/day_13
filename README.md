# day_13
    ___/* Выведи сообщение STRADA вертикально*/;___
showVerticalMessage("Strada");
function showVerticalMessage(text) {
    if (text[0] === 's') {
        return console.log('Ошибка: первая буква должна быть заглавной!')
    }
    
    if (typeof text !== "string") {
        return console.log("Ошибка: напиши буквенное выражение!");
    }
    for (let i = 0; i < 6; i++) {
        console.log(text[i]);
    }
}
___Метод indexOf() применяется в разных практических задачах. Вот реальные примеры, где он нужен:___

1️⃣ Валидация пользовательского ввода (формы, логины, пароли)
📌 Проверка, есть ли в строке запрещённые символы
Например, запрещаем использовать пробел в логине:

javascript
Копировать
Редактировать
function isValidUsername(username) {
    if (username.indexOf(" ") !== -1) {
        return "Ошибка: Логин не должен содержать пробелы!";
    }
    return "Логин корректен.";
}

console.log(isValidUsername("user123"));  // Логин корректен.
console.log(isValidUsername("user 123")); // Ошибка: Логин не должен содержать пробелы!
🛑 Полезно при создании форм регистрации.

2️⃣ Поиск ключевых слов в тексте (анализ текста, фильтры)
📌 Определяем, содержит ли сообщение запрещённые слова (например, для модерации чатов):

javascript
Копировать
Редактировать
function containsBadWords(message) {
    let badWords = ["спам", "реклама", "обман"];
    for (let word of badWords) {
        if (message.toLowerCase().indexOf(word) !== -1) {
            return "⚠️ Сообщение содержит запрещённые слова!";
        }
    }
    return "✅ Сообщение нормальное.";
}

console.log(containsBadWords("Купи этот товар, это НЕ реклама!")); // ⚠️ Сообщение содержит запрещённые слова!
console.log(containsBadWords("Привет, как дела?")); // ✅ Сообщение нормальное.
🚀 Применяется в чат-ботах, комментариях, форумах.

3️⃣ Обработка URL-адресов (перенаправления, навигация)
📌 Определяем, какой раздел сайта открыт, и выполняем действие:

javascript
Копировать
Редактировать
let url = window.location.href; // Получаем текущий URL

if (url.indexOf("profile") !== -1) {
    console.log("🔍 Открыт профиль пользователя.");
} else if (url.indexOf("settings") !== -1) {
    console.log("⚙️ Открыты настройки.");
} else {
    console.log("🏠 Главная страница.");
}
🌍 Полезно для SPA (одностраничных приложений), когда нужно менять содержимое без перезагрузки.

4️⃣ Работа с файлами (проверка расширения)
📌 Проверяем, загружен ли нужный формат файла:

javascript
Копировать
Редактировать
function isValidFile(fileName) {
    let validExtensions = [".jpg", ".png", ".gif"];
    for (let ext of validExtensions) {
        if (fileName.indexOf(ext) !== -1) {
            return "✅ Файл принят.";
        }
    }
    return "❌ Ошибка: Недопустимый формат!";
}

console.log(isValidFile("photo.jpg"));  // ✅ Файл принят.
console.log(isValidFile("document.pdf")); // ❌ Ошибка: Недопустимый формат!
📂 Используется при загрузке изображений или документов.

5️⃣ Поиск в массиве строк (быстрый фильтр)
📌 Фильтруем список по введённому тексту (например, поиск по товарам):

javascript
Копировать
Редактировать
let products = ["iPhone 13", "Samsung Galaxy", "MacBook Pro", "iPad Air"];

function searchProducts(query) {
    return products.filter(product => product.toLowerCase().indexOf(query.toLowerCase()) !== -1);
}

console.log(searchProducts("pro")); // ["MacBook Pro"]
console.log(searchProducts("galaxy")); // ["Samsung Galaxy"]
🔎 Используется в поисковых строках интернет-магазинов.

6️⃣ Поиск тегов или хэштегов в тексте
📌 Ищем хэштеги в посте пользователя:

javascript
Копировать
Редактировать
function findHashtags(post) {
    let words = post.split(" ");
    return words.filter(word => word.indexOf("#") === 0);
}

console.log(findHashtags("Сегодня отличный день! #happy #sunny")); // ["#happy", "#sunny"]
📲 Применяется в социальных сетях (Twitter, Instagram).

7️⃣ Поиск всех вхождений подстроки (выделение в тексте)
📌 Например, нужно подсветить слово в тексте:

javascript
Копировать
Редактировать
function highlightWord(text, word) {
    let pos = text.indexOf(word);
    while (pos !== -1) {
        console.log(`Слово "${word}" найдено на позиции ${pos}`);
        pos = text.indexOf(word, pos + 1);
    }
}

highlightWord("Hello world! Programming world is amazing.", "world");
// Вывод:
// Слово "world" найдено на позиции 6
// Слово "world" найдено на позиции 26
✨ Применяется для поисковых систем, редакторов, проверки орфографии.

📌 Вывод: Где indexOf() полезен?
✅ Валидация строк (проверка ввода, фильтры, запрещённые символы).
✅ Обработка текстов (поиск слов, выделение, работа с хэштегами).
✅ Работа с URL (анализ пути, редиректы, динамическая навигация).
✅ Обработка файлов (проверка расширения, поиск нужного типа).
✅ Фильтрация и поиск данных (поиск по списку, автодополнение).

👨‍💻 indexOf() — простой и быстрый способ находить подстроки без сложных регулярных выражений.
Если нужен более гибкий вариант, можно использовать match() с регулярками.



