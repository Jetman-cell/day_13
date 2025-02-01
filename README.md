# day_13
/* Выведи сообщение STRADA вертикально*/;
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
