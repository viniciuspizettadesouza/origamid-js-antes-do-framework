# origamid-js-antes-do-framework

https://origamid.com/slide/youtube/#/0101-javascript-antes-do-framework/13

CLASS
class SmoothScroll {
constructor(links, menu) {
this.linkElements = document.querySelectorAll(links);
this.menuElement = document.querySelector(menu);

    // Bind linka o this relacionado a classe SmoothScroll,
    // permanentemente ao handleClick
    this.handleClick = this.handleClick.bind(this);
    this.addScrollEvent();

}
handleClick(event) {
event.preventDefault();
const href = event.currentTarget.getAttribute("href");
const section = document.querySelector(href);
window.scrollTo({
top: section.offsetTop - (window.innerHeight - section.clientHeight) / 2,
behavior: "smooth"
});
}
addScrollEvent() {
this.linkElements.forEach(link =>
link.addEventListener("click", this.handleClick)
);
}
}

class ActiveSmoothScroll extends SmoothScroll {
constructor(links, menu, sections) {
// O super vai ativar o construtor da classe extendida
super(links, menu);
this.sectionElements = document.querySelectorAll(sections);

    this.handleScroll = this.handleScroll.bind(this);
    this.handleScroll();
    this.activeNavScroll();

}
handleScroll() {
this.sectionElements.forEach((section, i) => {
if (window.pageYOffset > section.offsetTop - window.innerHeight \* 0.5) {
this.linkElements[i].classList.add("active");
} else {
this.linkElements[i].classList.remove("active");
}
});
}
activeNavScroll() {
window.addEventListener("scroll", this.handleScroll);
}
}

new ActiveSmoothScroll("a[href^='#']", ".menu", "section");
