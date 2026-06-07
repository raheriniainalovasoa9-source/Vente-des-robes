
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Robe & Élégance - Boutique en ligne</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        *{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif;}
        body{background:#fef9f5;color:#2d2a2a;}
        nav{background:#fff;padding:1rem 2rem;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;position:sticky;top:0;z-index:100;box-shadow:0 2px 10px rgba(0,0,0,0.05);}
        .logo h1{font-family:'Playfair Display',serif;color:#c44536;font-size:1.5rem;}
        .logo span{font-size:0.7rem;color:#a35c4a;}
        .nav-links{display:flex;gap:1.5rem;list-style:none;}
        .nav-links a{text-decoration:none;color:#3e2c28;font-weight:500;}
        .nav-links a:hover,.nav-links a.active{color:#c44536;border-bottom:2px solid #c44536;}
        .cart-icon{position:relative;cursor:pointer;}
        .cart-count{position:absolute;top:-8px;right:-12px;background:#c44536;color:white;border-radius:50%;padding:2px 6px;font-size:0.7rem;}
        .page{display:none;padding:2rem;max-width:1300px;margin:0 auto;}
        .active-page{display:block;}
        .hero{background:linear-gradient(105deg,#fff1e8,#ffe6db);border-radius:36px;padding:2rem;display:flex;flex-wrap:wrap;justify-content:space-between;align-items:center;margin-bottom:2rem;}
        .hero-text h2{font-size:2rem;font-family:'Playfair Display',serif;}
        .btn{background:#c44536;color:white;padding:10px 25px;border:none;border-radius:40px;cursor:pointer;font-weight:600;}
        .btn:hover{background:#a23426;}
        .section-title{font-size:1.8rem;margin:2rem 0 1rem;border-left:5px solid #c44536;padding-left:1rem;font-family:'Playfair Display',serif;}
        .grid-produits{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:1.5rem;}
        .carte-robe{background:white;border-radius:20px;overflow:hidden;text-align:center;padding-bottom:1rem;box-shadow:0 5px 15px rgba(0,0,0,0.05);}
        .carte-robe img{width:100%;height:280px;object-fit:cover;}
        .carte-robe h3{margin:0.8rem 0 0.2rem;}
        .prix{color:#c44536;font-weight:700;font-size:1.2rem;}
        .btn-acheter{background:#2b211e;color:white;border:none;padding:8px 20px;border-radius:40px;margin-top:8px;cursor:pointer;}
        .btn-acheter:hover{background:#c44536;}
        .cart-sidebar{position:fixed;top:0;right:-400px;width:380px;height:100%;background:white;box-shadow:-2px 0 20px rgba(0,0,0,0.1);z-index:1000;transition:0.3s;padding:1.5rem;display:flex;flex-direction:column;}
        .cart-sidebar.open{right:0;}
        .cart-header{display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid #ddd;padding-bottom:1rem;}
        .cart-items{flex:1;overflow-y:auto;margin:1rem 0;}
        .cart-item{display:flex;justify-content:space-between;align-items:center;padding:0.8rem 0;border-bottom:1px solid #eee;}
        .cart-item-info{flex:1;}
        .cart-item-title{font-weight:500;}
        .cart-item-price{color:#c44536;font-size:0.9rem;}
        .remove-item{background:none;border:none;color:#999;cursor:pointer;font-size:1.2rem;}
        .remove-item:hover{color:#c44536;}
        .cart-total{font-weight:700;font-size:1.3rem;border-top:2px solid #ddd;padding-top:1rem;text-align:right;}
        .checkout-btn{background:#c44536;color:white;border:none;padding:12px;border-radius:40px;margin-top:1rem;cursor:pointer;width:100%;font-weight:600;}
        .whatsapp-btn{background:#25D366;color:white;border:none;padding:12px;border-radius:40px;margin-top:0.5rem;cursor:pointer;width:100%;font-weight:600;display:flex;align-items:center;justify-content:center;gap:8px;}
        .whatsapp-btn:hover{background:#128C7E;}
        .overlay{position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.5);z-index:999;display:none;}
        .toast-msg{position:fixed;bottom:20px;right:20px;background:#2b211e;color:white;padding:10px 20px;border-radius:40px;opacity:0;transition:0.2s;z-index:1001;}
        footer{text-align:center;padding:2rem;background:#f3eae5;margin-top:2rem;font-size:0.8rem;}
        .contact-bar{background:#fff;padding:0.8rem 2rem;display:flex;justify-content:center;gap:2rem;flex-wrap:wrap;border-top:1px solid #f0e0d8;border-bottom:1px solid #f0e0d8;}
        .contact-bar a{text-decoration:none;color:#3e2c28;font-weight:500;display:flex;align-items:center;gap:8px;}
        .contact-bar a i{font-size:1.2rem;}
        .contact-bar a.whatsapp{color:#25D366;}
        .contact-bar a.phone{color:#c44536;}
        .contact-bar a:hover{opacity:0.8;}
        @media(max-width:700px){nav{flex-direction:column;gap:0.5rem;}.cart-sidebar{width:100%;right:-100%;}.contact-bar{gap:1rem;font-size:0.8rem;}}
    </style>
</head>
<body>

<nav>
    <div class="logo"><h1>Robe & Élégance <span>✧ robes d'exception</span></h1></div>
    <ul class="nav-links">
        <li><a href="#" data-page="accueil" class="nav-link active">Accueil</a></li>
        <li><a href="#" data-page="produits" class="nav-link">Produits</a></li>
        <li><a href="#" data-page="offre" class="nav-link">Offre</a></li>
        <li><a href="#" data-page="apropos" class="nav-link">À propos</a></li>
        <li><a href="#" data-page="contact" class="nav-link">Contact</a></li>
    </ul>
    <div class="cart-icon" id="cartIcon"><i class="fas fa-shopping-bag fa-lg"></i><span class="cart-count" id="cartCount">0</span></div>
</nav>

<!-- BARRE DE CONTACT FIXE (WhatsApp + Téléphone) -->
<div class="contact-bar">
    <a href="https://wa.me/261341234567?text=Bonjour%20je%20souhaite%20avoir%20des%20informations%20sur%20vos%20robes" target="_blank" class="whatsapp">
        <i class="fab fa-whatsapp"></i> WhatsApp : +261 34 12 345 67
    </a>
    <a href="tel:+261341234567" class="phone">
        <i class="fas fa-phone-alt"></i> Téléphone : +261 34 12 345 67
    </a>
</div>

<!-- PAGES -->
<div id="accueil" class="page active-page">
    <div class="hero"><div class="hero-text"><h2>L'élégance au quotidien</h2><p>Livraison offerte dès 120 000 Ar.</p><button class="btn" id="heroShopBtn">Voir les produits →</button></div>
    <img src="https://images.unsplash.com/photo-1539008835657-9e8e9680c956?w=300&h=350&fit=crop" style="width:260px;border-radius:28px;"></div>
    <div class="section-title">✨ Nos coups de cœur</div><div class="grid-produits" id="accueil-highlights"></div>
</div>

<div id="produits" class="page"><div class="section-title">👗 Collection Printemps-Été</div><div class="grid-produits" id="all-products-grid"></div></div>

<div id="offre" class="page"><div class="offre-box" style="background:#f3e1d8;border-radius:48px;padding:2rem;text-align:center;"><span style="background:#c44536;color:white;padding:5px 15px;border-radius:60px;">🎁 OFFRE EXCLUSIVE</span><h2 style="margin:1rem 0;">-20% sur votre première commande</h2><p>Code: <strong>BIENVENUE20</strong></p><button class="btn" id="offreShopBtn">Profiter →</button></div>
<div style="margin-top:2rem;"><div class="section-title">🔥 Offres flash</div><div class="grid-produits" id="offre-produits"></div></div></div>

<div id="apropos" class="page"><div style="display:flex;gap:2rem;flex-wrap:wrap;background:white;padding:2rem;border-radius:32px;"><div><h2 style="font-family:'Playfair Display';">Notre histoire</h2><p>Robe & Élégance, une passion pour la mode responsable. Livraison Madagascar.</p><p>✨ Qualité premium<br>✨ Éco-emballages</p><p><i class="fab fa-whatsapp" style="color:#25D366;"></i> Contactez-nous sur WhatsApp pour toute question !</p></div>
<img src="https://images.unsplash.com/photo-1483985988355-763728e1935b?w=400&h=250&fit=crop" style="border-radius:32px;width:100%;max-width:300px;"></div></div>

<div id="contact" class="page"><div class="section-title">📬 Contactez-nous</div><div class="form-contact" style="background:white;padding:2rem;border-radius:32px;max-width:600px;">
    <form id="contactForm"><input type="text" id="nom" placeholder="Nom" style="width:100%;padding:12px;margin-bottom:1rem;border-radius:40px;border:1px solid #e2cfc7;"><input type="email" id="email" placeholder="Email" style="width:100%;padding:12px;margin-bottom:1rem;border-radius:40px;border:1px solid #e2cfc7;"><textarea id="message" rows="3" placeholder="Message" style="width:100%;padding:12px;margin-bottom:1rem;border-radius:20px;border:1px solid #e2cfc7;"></textarea><button type="submit" class="btn">Envoyer</button></form>
    <div style="margin-top:1.5rem;padding-top:1rem;border-top:1px solid #eee;text-align:center;">
        <p><strong>Ou contactez-nous directement :</strong></p>
        <a href="https://wa.me/261341234567?text=Bonjour%20je%20souhaite%20commander%20une%20robe" target="_blank" style="display:inline-block;background:#25D366;color:white;padding:10px 20px;border-radius:40px;margin:0.5rem;text-decoration:none;"><i class="fab fa-whatsapp"></i> WhatsApp</a>
        <a href="tel:+261341234567" style="display:inline-block;background:#c44536;color:white;padding:10px 20px;border-radius:40px;margin:0.5rem;text-decoration:none;"><i class="fas fa-phone-alt"></i> Appeler</a>
    </div>
</div></div>

<!-- PANIER LATERAL -->
<div class="overlay" id="overlay"></div>
<div class="cart-sidebar" id="cartSidebar">
    <div class="cart-header"><h3>Mon Panier</h3><i class="fas fa-times" id="closeCart" style="cursor:pointer;font-size:1.3rem;"></i></div>
    <div class="cart-items" id="cartItems"><p style="text-align:center;color:#999;">Votre panier est vide</p></div>
    <div class="cart-total" id="cartTotal">Total: 0 Ar</div>
    <button class="checkout-btn" id="checkoutBtn">📦 Valider la commande</button>
    <button class="whatsapp-btn" id="whatsappOrderBtn"><i class="fab fa-whatsapp"></i> Commander via WhatsApp</button>
</div>

<footer>© 2026 Robes & Élégance — Livraison Madagascar 48h-72h — <i class="fab fa-whatsapp"></i> +261 34 12 345 67</footer>
<div id="toastMsg" class="toast-msg"></div>

<script>
// Catalogue produits (prix en Ariary)
const robes = [
    { id: 1, nom: "Robe Flore Jardin", prixAr: 132000, image: "https://images.unsplash.com/photo-1595777457583-95e059d581b8?w=400&h=500&fit=crop", highlight: true, offre: true },
    { id: 2, nom: "Robe Soirée Lunée", prixAr: 120000, image: "https://images.unsplash.com/photo-1566174053879-31528523f8ae?w=400&h=500&fit=crop", highlight: false, offre: true },
    { id: 3, nom: "Robe Été", prixAr: 96000, image: "https://images.unsplash.com/photo-1515372039744-b8f02a3ae446?w=400&h=500&fit=crop", highlight: true, offre: false },
    { id: 4, nom: "Robe Cachemire", prixAr: 135000, image: "https://images.unsplash.com/photo-1581044777550-4cfa60707c03?w=400&h=500&fit=crop", highlight: false, offre: false },
    { id: 5, nom: "Robe Collée", prixAr: 100000, image: "https://images.unsplash.com/photo-1496747611176-843222e1e57c?w=400&h=500&fit=crop", highlight: true, offre: true },
    { id: 6, nom: "Robe Maxi Vintage", prixAr: 112000, image: "https://images.unsplash.com/photo-1495385794356-15371f348c31?w=400&h=500&fit=crop", highlight: false, offre: false },
    { id: 7, nom: "Robe Chic Plissée", prixAr: 122000, image: "https://images.unsplash.com/photo-1539008835657-9e8e9680c956?w=400&h=500&fit=crop", highlight: false, offre: true }
];

let panier = JSON.parse(localStorage.getItem('panier')) || [];

function sauvegarderPanier() { localStorage.setItem('panier', JSON.stringify(panier)); miseAJourAffichagePanier(); miseAJourCompteur(); }

function miseAJourCompteur() { document.getElementById('cartCount').innerText = panier.reduce((s,item)=> s+item.quantite, 0); }

function miseAJourAffichagePanier() {
    const container = document.getElementById('cartItems');
    const totalSpan = document.getElementById('cartTotal');
    if(panier.length === 0) { container.innerHTML = '<p style="text-align:center;color:#999;">Votre panier est vide</p>'; totalSpan.innerText = 'Total: 0 Ar'; return; }
    let html = '', total = 0;
    panier.forEach(item => {
        total += item.prixAr * item.quantite;
        html += `<div class="cart-item"><div class="cart-item-info"><div class="cart-item-title">${item.nom}</div><div class="cart-item-price">${item.prixAr.toLocaleString('fr-MG')} Ar</div><div>Quantité: ${item.quantite}</div></div><button class="remove-item" data-id="${item.id}"><i class="fas fa-trash-alt"></i></button></div>`;
    });
    container.innerHTML = html;
    totalSpan.innerText = `Total: ${total.toLocaleString('fr-MG')} Ar`;
    document.querySelectorAll('.remove-item').forEach(btn => btn.addEventListener('click', (e) => { supprimerDuPanier(parseInt(btn.dataset.id)); }));
}

function ajouterAuPanier(robe) {
    const existant = panier.find(p => p.id === robe.id);
    if(existant) existant.quantite++;
    else panier.push({...robe, quantite: 1});
    sauvegarderPanier();
    toastMsg(`✨ ${robe.nom} ajoutée au panier`);
}

function supprimerDuPanier(id) { panier = panier.filter(p => p.id !== id); sauvegarderPanier(); toastMsg('Article retiré'); }

function toastMsg(msg) { const t = document.getElementById('toastMsg'); t.textContent = msg; t.style.opacity = '1'; setTimeout(()=> t.style.opacity='0', 2000); }

function genererCarte(r) { return `<div class="carte-robe"><img src="${r.image}" alt="${r.nom}"><h3>${r.nom}</h3><div class="prix">${r.prixAr.toLocaleString('fr-MG')} Ar</div><button class="btn-acheter" data-id="${r.id}" data-nom="${r.nom}" data-prix="${r.prixAr}">Ajouter au panier 🛒</button></div>`; }

function afficherHighlights() { document.getElementById('accueil-highlights').innerHTML = robes.filter(r=>r.highlight).map(genererCarte).join(''); }
function afficherTous() { document.getElementById('all-products-grid').innerHTML = robes.map(genererCarte).join(''); }
function afficherOffres() { document.getElementById('offre-produits').innerHTML = robes.filter(r=>r.offre).map(genererCarte).join(''); }

function attacherEvents() { document.querySelectorAll('.btn-acheter').forEach(btn => { btn.removeEventListener('click', handler); btn.addEventListener('click', handler); }); }
function handler(e) { const id = parseInt(e.currentTarget.dataset.id); const robe = robes.find(r=>r.id===id); if(robe) ajouterAuPanier(robe); }

// Générer le message WhatsApp avec le récapitulatif de la commande
function genererMessageWhatsApp() {
    if(panier.length === 0) return null;
    let message = "🛍️ *MA COMMANDE Robe & Élégance* 🛍️%0A%0A";
    let total = 0;
    panier.forEach(item => {
        const prixTotalItem = item.prixAr * item.quantite;
        total += prixTotalItem;
        message += `▪️ ${item.nom} x${item.quantite} : ${prixTotalItem.toLocaleString('fr-MG')} Ar%0A`;
    });
    message += `%0A📦 *TOTAL : ${total.toLocaleString('fr-MG')} Ar*%0A%0A`;
    message += `📍 Livraison : Madagascar%0A`;
    message += `💬 Merci de confirmer ma commande !%0A`;
    return message;
}

// Bouton de commande normal (simulation)
document.getElementById('checkoutBtn')?.addEventListener('click',()=>{ 
    if(panier.length===0) toastMsg('Panier vide'); 
    else { 
        toastMsg('✅ Commande validée ! Un conseiller vous contactera sous 24h.'); 
        panier=[]; 
        sauvegarderPanier(); 
        document.getElementById('cartSidebar').classList.remove('open'); 
        document.getElementById('overlay').style.display='none'; 
    } 
});

// Bouton WhatsApp - envoie directement le récapitulatif
document.getElementById('whatsappOrderBtn')?.addEventListener('click',()=>{
    if(panier.length===0) { toastMsg('Panier vide'); return; }
    const message = genererMessageWhatsApp();
    if(message) {
        const numeroWhatsApp = "261341234567"; // Numéro du vendeur (sans le +)
        const url = `https://wa.me/${numeroWhatsApp}?text=${message}`;
        window.open(url, '_blank');
        toastMsg('Redirection vers WhatsApp...');
        // Optionnel : vider le panier après envoi ?
        // panier = []; sauvegarderPanier();
        // document.getElementById('cartSidebar').classList.remove('open');
        // document.getElementById('overlay').style.display='none';
    }
});

// Navigation
const pages = { accueil:document.getElementById('accueil'), produits:document.getElementById('produits'), offre:document.getElementById('offre'), apropos:document.getElementById('apropos'), contact:document.getElementById('contact') };
function showPage(id) { Object.values(pages).forEach(p=>p.classList.remove('active-page')); pages[id].classList.add('active-page'); document.querySelectorAll('.nav-link').forEach(l=>{l.classList.toggle('active', l.dataset.page===id);}); if(id==='accueil') afficherHighlights(); if(id==='produits') afficherTous(); if(id==='offre') afficherOffres(); setTimeout(attacherEvents,20); }
document.querySelectorAll('.nav-link').forEach(l=>l.addEventListener('click',(e)=>{e.preventDefault(); showPage(l.dataset.page);}));
document.getElementById('heroShopBtn')?.addEventListener('click',()=>showPage('produits'));
document.getElementById('offreShopBtn')?.addEventListener('click',()=>showPage('produits'));

// Panier UI
document.getElementById('cartIcon').addEventListener('click',()=>{ document.getElementById('cartSidebar').classList.add('open'); document.getElementById('overlay').style.display='block'; });
document.getElementById('closeCart').addEventListener('click',()=>{ document.getElementById('cartSidebar').classList.remove('open'); document.getElementById('overlay').style.display='none'; });
document.getElementById('overlay').addEventListener('click',()=>{ document.getElementById('cartSidebar').classList.remove('open'); document.getElementById('overlay').style.display='none'; });

// Contact formulaire
document.getElementById('contactForm')?.addEventListener('submit',(e)=>{ e.preventDefault(); const n=document.getElementById('nom').value.trim(), em=document.getElementById('email').value.trim(), msg=document.getElementById('message').value.trim(); if(!n||!em||!msg) toastMsg('Tous les champs requis'); else if(!em.includes('@')) toastMsg('Email invalide'); else { toastMsg(`Merci ${n} ! Réponse sous 24h.`); e.target.reset(); } });

// Init
afficherHighlights(); afficherTous(); afficherOffres(); attacherEvents(); miseAJourAffichagePanier(); miseAJourCompteur();
</script>
</body>
</html>
