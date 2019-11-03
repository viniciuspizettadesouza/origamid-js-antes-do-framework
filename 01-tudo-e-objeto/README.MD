# origamid-js-antes-do-framework

https://origamid.com/slide/youtube/#/0101-javascript-antes-do-framework/2

TUDO É OBJETO
Um objeto possui propriedades e métodos quem podem ser diretos ou herdados (protótipo).

// Objeto Literal
const menu = {
selector: ".principal",
active() {
const menuElement = document.querySelector(this.selector);
menuElement.classList.add("active");
}
};

menu.selector; // ".principal";
menu.active(); // adicionar active ao menu
menu.hasOwnProperty("class"); // método herdado

["10", "20", "30"].map(Number); // [10, 20, 30];
"JavaScript".toUpperCase(); // JAVASCRIPT

const body = document.querySelector("body");
body.classList.add("js"); // adiciona JS ao Body

    Todo objeto possui um protótipo, menos o null e o undefined (este não é um objeto).
