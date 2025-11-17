# teste-site  

Mehdi Roh
15:18 (il y a 0 minute)
À moi

// Animation d'apparition du contenu
document.addEventListener("DOMContentLoaded", () => {
const elements = document.querySelectorAll(".fade");
elements.forEach((el, i) => {
setTimeout(() => {
el.classList.add("visible");
}, i * 200);
});
});

// Fonction du bouton
function action() {
const msg = document.createElement("div");
msg.className = "popup";
msg.textContent = "Merci ! Du contenu arrive très bientôt...";
document.body.appendChild(msg);

setTimeout(() => {
msg.classList.add("show");
}, 10);

setTimeout(() => {
msg.classList.remove("show");
setTimeout(() => msg.remove(), 300);
}, 2000);
}

// Mode clair/sombre
function toggleTheme() {
document.body.classList.toggle("light");
}
/* Apparition fade */
.fade {
opacity: 0;
transform: translateY(20px);
transition: 0.6s;
}

.fade.visible {
opacity: 1;
transform: translateY(0);
}

/* Popup message */
.popup {
position: fixed;
bottom: 30px;
left: 50%;
transform: translateX(-50%);
background: #111;
color: white;
padding: 12px 25px;
border-radius: 10px;
opacity: 0;
transition: 0.3s;
}

.popup.show {
opacity: 1;
transform: translateX(-50%) translateY(-10px);
}

/* Mode light */
body.light {
background: #f5f5f5;
color: #111;
}
<h1 class="fade">Mon Site Dark</h1>
<p class="fade">Bienvenue dans l'univers sombre et moderne.</p>
<button onclick="action()" class="fade">En savoir plus</button>
<button onclick="toggleTheme()" class="fade">Changer de thème</button>
