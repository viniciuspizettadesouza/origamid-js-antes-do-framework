# origamid-js-antes-do-framework

https://origamid.com/slide/youtube/#/0101-javascript-antes-do-framework/12

EXPRESSÕES
const grupoA = 100;
const grupoB = 300;
const vencedor = grupoA > grupoB ? "Grupo A Venceu" : "Grupo B Venceu";

const numeros = [2, 3, 4, 5, 6];
const total = numeros.filter(numero => numero > 4);

const active = true;
const button = active && "Botão está ativo";

JSX

// JSX
<button onClick={event => event.target.classList.add("active")}>Button</button>

Vue

<button @click="({target}) => target.classList.add('active')">Button</button>

