<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Messagerie Anonyme</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f2f2f2; padding: 20px; }
    .container { max-width: 500px; margin: auto; background: white; padding: 20px; border-radius: 8px; }
    textarea { width: 100%; height: 100px; margin-top: 10px; padding: 10px; border-radius: 4px; border: 1px solid #ccc; }
    button { margin-top: 10px; padding: 10px 20px; background: #007BFF; color: white; border: none; border-radius: 4px; cursor: pointer; }
    .messages { margin-top: 20px; background: #eee; padding: 10px; border-radius: 4px; min-height: 100px; }
    .message-item { margin-bottom: 10px; padding: 8px; background: #fff; border-radius: 4px; }
  </style>
</head>
<body>
  <div class="container">
    <h2>Messagerie Anonyme</h2>
    <textarea id="message" placeholder="Écris ton message ici..."></textarea>
    <button onclick="envoyerMessage()">Envoyer</button>

    <div class="messages" id="messages">
      <h4>Messages reçus :</h4>
    </div>
  </div>
<script>
    const messages = [];

    function envoyerMessage() {
      const textarea = document.getElementById("message");
      const msg = textarea.value.trim();
      if (msg === "") return;

      messages.unshift(msg);
      textarea.value = "";
      afficherMessages();
    }

    function afficherMessages() {
      const box = document.getElementById("messages");
      box.innerHTML = "<h4>Messages reçus :</h4>";
      messages.forEach(m => {
        const div = document.createElement("div");
        div.className = "message-item";
        div.textContent = m;
        box.appendChild(div);
      });
    }
  </script>

</body>
