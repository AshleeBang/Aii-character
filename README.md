# Aii-character <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AI Character</title>
  <link rel="stylesheet" href="style.css"/>
</head>
<body>
  <div class="chat-container">
    <h1>AI Character</h1>
    <div id="chat-box"></div>
    <input type="text" id="user-input" placeholder="Say something..."/>
    <button onclick="sendMessage()">Send</button>
  </div>
  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  margin: 0;
  padding: 20px;
}

.chat-container {
  max-width: 500px;
  margin: auto;
  background: white;
  padding: 20px;
  border-radius: 10px;
}

#chat-box {
  height: 300px;
  overflow-y: auto;
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}

input[type="text"] {
  width: 70%;
  padding: 10px;
}

button {
  padding: 10px 15px;
}
function sendMessage() {
  const input = document.getElementById("user-input");
  const chatBox = document.getElementById("chat-box");

  const userText = input.value;
  if (!userText.trim()) return;

  const userMessage = `<p><strong>You:</strong> ${userText}</p>`;
  const aiMessage = `<p><strong>AI:</strong> ${getAIResponse(userText)}</p>`;

  chatBox.innerHTML += userMessage + aiMessage;
  input.value = "";
  chatBox.scrollTop = chatBox.scrollHeight;
}

function getAIResponse(input) {
  return "I'm just a simple AI character for now!";
}
