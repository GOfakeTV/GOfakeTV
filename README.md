- 👋 Hi, I’m @GOfakeTV
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
GOfakeTV/GOfakeTV is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mon Site Vinted</title>
    <style>
        /* Ajoutez vos styles CSS ici */
    </style>
</head>

<body>
    <nav style="background-color: #f8f9fa; padding: 10px;">
        <div style="text-align: center;">
            <h1>Vinted-like</h1>
            <form style="margin-top: 10px;">
                <input type="search" placeholder="Recherche" aria-label="Search">
                <button type="submit">Rechercher</button>
            </form>
        </div>
    </nav>

    <div style="margin: 20px;">
        <div style="display: flex; flex-wrap: wrap;">
            <!-- Annonces -->
            <div style="flex: 0 0 30%; margin: 10px; border: 1px solid #ccc; padding: 10px;">
                <h2>Nom du Produit</h2>
                <p>Description du produit.</p>
                <button onclick="toggleFavori(this)">❤️ Ajouter aux favoris</button>
            </div>
            <!-- Plus d'annonces ici -->

            <!-- Panier -->
            <div style="flex: 0 0 60%; margin: 10px; border: 1px solid #ccc; padding: 10px;">
                <h2>Panier</h2>
                <ul id="panier">
                    <!-- Contenu du panier ici -->
                </ul>
            </div>
        </div>

        <!-- Messagerie -->
        <div style="margin-top: 50px;">
            <h2>Messagerie</h2>
            <div id="messages" style="border: 1px solid #ccc; padding: 10px;">
                <!-- Messages ici -->
            </div>
            <input type="text" id="messageInput" placeholder="Votre message...">
            <button onclick="envoyerMessage()">Envoyer</button>
        </div>
    </div>

    <script>
        // Tableau pour stocker les annonces
        let annonces = [
            // Structure des annonces
            // { id: 1, nom: "Nom du Produit", description: "Description du produit", favori: false },
            // ...
        ];

        // Tableau pour stocker les messages
        let messages = [];

        // Fonction pour ajouter ou retirer une annonce des favoris
        function toggleFavori(button) {
            const index = button.parentElement.dataset.index;
            annonces[index].favori = !annonces[index].favori;
            updateFavoriButton(button, annonces[index].favori);
        }

        // Fonction pour envoyer un message
        function envoyerMessage() {
            const messageInput = document.getElementById('messageInput');
            const texte = messageInput.value;
            if (texte.trim() === '') return;
            const message = { expéditeur: 'Vendeur', texte: texte };
            messages.push(message);
            afficherMessages();
            messageInput.value = '';
        }

        // Met à jour l'apparence du bouton de favori
        function updateFavoriButton(button, estFavori) {
            if (estFavori) {
                button.innerHTML = '❤️ Retirer des favoris';
            } else {
                button.innerHTML = '❤️ Ajouter aux favoris';
            }
        }

        // Fonction pour afficher les messages
        function afficherMessages() {
            const messagesDiv = document.getElementById('messages');
            messagesDiv.innerHTML = '';
            messages.forEach(message => {
                const messageDiv = document.createElement('div');
                messageDiv.innerText = `${message.expéditeur}: ${message.texte}`;
                messagesDiv.appendChild(messageDiv);
            });
        }

        // Appel de la fonction d'initialisation pour afficher les annonces
        initAnnonces();

        // Fonction d'initialisation pour afficher les annonces
        function initAnnonces() {
            // Code d'initialisation des annonces ici
        }
    </script>
</body>

</html>
