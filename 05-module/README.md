# origamid-js-antes-do-framework

https://origamid.com/slide/youtube/#/0101-javascript-antes-do-framework/8

MODULE
Os módulos servem para quebrarmos o código em diferente arquivos, para facilitar a organização e compartilhamento de código comum.

<!-- Só funciona em servidor, seja local ou online
Não irá funcionar se você abrir o html direto -->
<script type="module" src="./script.js"></script>

// quadrado.js
export function areaQuadrado(l) {
return l \* l;
}

export function perimetroQuadrado(l) {
return 4 \* l;
}

// numeroAleatorio.js
export default function numeroAleatorio() {
return Math.random();
}

// Circulo.js
import numeroAleatorio from "./numeroAleatorio.js";

function area(raio) {
return Math.PI _ raio _ raio;
}

function circunferencia(raio) {
return 2 _ raio _ Math.PI;
}

function aleatorio() {
return numeroAleatorio();
}

const Circulo = {
area,
circunferencia,
aleatorio
};

export default Circulo;

Qualquer arquivo pode importar código de outro. Ele irá carregar apenas uma vez o arquivo, independente de quantas vezes você importar o mesmo em outros arquivos.

// script.js
import { areaQuadrado, perimetroQuadrado } from "./quadrado.js";
import numeroAleatorio from "./numeroAleatorio.js";
import Circulo from "./Circulo.js";

areaQuadrado(4);
perimetroQuadrado(5);
numeroAleatorio();
Circulo.area(5);
Circulo.circunferencia(5);
Circulo.aleatorio();
