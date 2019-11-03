# origamid-js-antes-do-framework

https://origamid.com/slide/youtube/#/0101-javascript-antes-do-framework/5

ARROW FUNCTION
A principal diferença é o contexto do this. A arrow function não cria o próprio this.

const upperName = function(name) {
  return name.toUpperCase();
};
upperName("André"); // ANDRÉ

const lowerName = name => {
  return name.toLowerCase();
};
lowerName("Rafael"); // rafael

const countLetters = word => word.length;
countLetters("Rafael"); // 6

O this faz referência ao objeto criado pela função. A arrow function consegue ignorar isso, e manter como referência o objeto pai.

class Menu {
  constructor(menu) {
    this.menuElement = document.querySelector(menu);
    this.activeClass = "active";
  }
  addActiveEvent() {
    // sem o arrow function ele não iria funcionar
    this.menuElement.addEventListener("click", event =>
      event.target.classList.add(this.activeClass)
    );
  }
}

const menu = new Menu(".principal");
menu.addActiveEvent();