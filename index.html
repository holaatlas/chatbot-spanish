<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Chatbot Spanish - Introductions</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto+Slab&display=swap" rel="stylesheet" />
  <style>
    body {
      font-family: 'Roboto Slab', serif;
      background-color: #F3EFE3;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      height: 100vh;
      color: #A84339;
    }
    header {
      background-color: #CB9180;
      width: 100%;
      padding: 15px 0;
      text-align: center;
      box-shadow: 0 3px 8px rgba(0,0,0,0.2);
    }
    header img {
      height: 60px;
    }
    #accent-selector {
      margin-top: 10px;
      display: flex;
      justify-content: center;
      gap: 15px;
    }
    .flag-btn {
      border: none;
      background: transparent;
      font-size: 28px;
      cursor: pointer;
      transition: transform 0.2s ease;
    }
    .flag-btn:hover {
      transform: scale(1.2);
    }
    .selected {
      border-bottom: 3px solid #A84339;
    }
    #chat-container {
      flex-grow: 1;
      width: 90%;
      max-width: 600px;
      background: white;
      border-radius: 12px;
      box-shadow: 0 0 12px rgba(168,67,57,0.3);
      padding: 20px;
      overflow-y: auto;
      margin: 20px 0;
    }
    #messages {
      display: flex;
      flex-direction: column;
      gap: 15px;
      max-height: 70vh;
      overflow-y: auto;
      padding-right: 10px;
    }
    .message {
      padding: 12px 16px;
      border-radius: 20px;
      max-width: 75%;
      line-height: 1.4;
      font-size: 1.1em;
    }
    .bot {
      background-color: #CB9180;
      color: white;
      align-self: flex-start;
      box-shadow: 0 2px 5px rgba(168,67,57,0.6);
    }
    .user {
      background-color: #A84339;
      color: white;
      align-self: flex-end;
      box-shadow: 0 2px 5px rgba(203,145,128,0.7);
    }
    #feedback {
      color: #A84339;
      font-weight: bold;
      margin-top: 5px;
      min-height: 20px;
      font-size: 0.9em;
      font-style: italic;
    }
    #input-area {
      display: flex;
      width: 90%;
      max-width: 600px;
      margin-bottom: 20px;
      gap: 10px;
    }
    #user-input {
      flex-grow: 1;
      font-size: 1.1em;
      padding: 10px 15px;
      border-radius: 25px;
      border: 2px solid #A84339;
      outline: none;
      color: #A84339;
    }
    #send-btn, #mic-btn {
      background-color: #A84339;
      border: none;
      color: white;
      font-size: 1.3em;
      padding: 0 15px;
      border-radius: 50%;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    #send-btn:hover, #mic-btn:hover {
      background-color: #CB9180;
    }
    #send-btn:disabled {
      background-color: #e0bfb7;
      cursor: not-allowed;
    }
  </style>
</head>
<body>
  <header>
    <img src="images/Atlas_Color.png" alt="Logo Atlas Language Academy" />
  </header>

  <!-- Only one accent button for Spain -->
  <div id="accent-selector">
    <button class="flag-btn selected" data-accent="es-ES">🇪🇸</button>
  </div>

  <div id="chat-container" aria-live="polite" aria-atomic="true">
    <div id="messages"></div>
    <div id="feedback" role="alert"></div>
  </div>

  <div id="input-area">
    <input type="text" id="user-input" aria-label="Your response" placeholder="Escribe o usa el micrófono..." />
    <button id="mic-btn" aria-label="Activate microphone">🎤</button>
    <button id="send-btn" aria-label="Send message">➤</button>
  </div>

  <script>
    const messages = document.getElementById('messages');
    const input = document.getElementById('user-input');
    const sendBtn = document.getElementById('send-btn');
    const micBtn = document.getElementById('mic-btn');
    const feedback = document.getElementById('feedback');
    const flags = document.querySelectorAll('.flag-btn');

    let selectedVoice = null;
    let selectedAccent = 'es-ES';
    let step = 0, userName = "", userAge = null, userOrigin = "", userAdj = "";

    // Voice loading and selection
    function loadVoices() {
      return new Promise(resolve => {
        let voices = speechSynthesis.getVoices();
        if (voices.length) return resolve(voices);
        speechSynthesis.onvoiceschanged = () => resolve(speechSynthesis.getVoices());
      });
    }

    async function selectVoice() {
      const voices = await loadVoices();
      // Prefer Google natural Spanish (Spain) voice
      selectedVoice =
        voices.find(v => v.lang === "es-ES" && v.name.includes("Google español")) ||
        voices.find(v => v.lang === "es-ES") ||
        null;

      if (!selectedVoice) {
        feedback.textContent = "No hay voz natural de España disponible en tu navegador.";
      } else {
        feedback.textContent = "";
      }
      return selectedVoice;
    }

    async function speak(text) {
      if (!selectedVoice) await selectVoice();
      if (!selectedVoice) {
        feedback.textContent = "No se encontró voz para la síntesis de habla.";
        return;
      }
      // Stop any currently speaking utterance
      if (speechSynthesis.speaking) speechSynthesis.cancel();
      const utterance = new SpeechSynthesisUtterance(text);
      utterance.voice = selectedVoice;
      utterance.lang = selectedAccent;
      speechSynthesis.speak(utterance);
    }

    function addMessage(text, sender) {
      const msgDiv = document.createElement('div');
      msgDiv.classList.add('message', sender);
      msgDiv.textContent = text;
      messages.appendChild(msgDiv);
      messages.scrollTop = messages.scrollHeight;
    }

    function capitalize(s) {
      return s.charAt(0).toUpperCase() + s.slice(1);
    }

    async function respond(text) {
      addMessage(text, 'bot');
      await speak(text);
    }

    async function handleResponse(text) {
      const inputLower = text.trim().toLowerCase();
      feedback.textContent = "";

      if (inputLower.includes("tonto") || inputLower.includes("malo")) {
        await respond("Por favor, usa un lenguaje apropiado. 🙏");
        return;
      }

      if (inputLower.includes("y tú")) {
        if (step === 1) return respond("Soy de Madrid.");
        if (step === 2) return respond("Tengo veinticinco años.");
        if (step === 3) return respond("Soy inteligente y creativo.");
        return respond("¡Qué bien! 😊");
      }

      if (step === 0) {
        const name = text.match(/me llamo (\w+)/i)?.[1] || text.match(/soy (\w+)/i)?.[1] || text.split(" ")[0];
        userName = capitalize(name);
        await respond(`¡Mucho gusto, ${userName}! ¿De dónde eres?`);
        step++;
      } else if (step === 1) {
        if (inputLower.startsWith("soy de ")) {
          userOrigin = text.slice(7).trim();
          await respond("¡Genial! ¿Cuántos años tienes?");
          step++;
        } else {
          feedback.textContent = "Por favor, responde con 'Soy de [lugar]'.";
        }
      } else if (step === 2) {
        const age = text.match(/\b(\d{1,3})\b/);
        if (age && +age[1] >= 1 && +age[1] <= 120) {
          userAge = +age[1];
          await respond(`Perfecto, tienes ${userAge} años. ¿Cómo te describirías con un adjetivo?`);
          step++;
        } else {
          feedback.textContent = "Por favor, introduce un número válido entre 1 y 120.";
        }
      } else if (step === 3) {
        userAdj = text.trim();
        if (userAdj.length < 2) {
          feedback.textContent = "Por favor, introduce un adjetivo válido.";
          return;
        }
        await respond(`¡Muy bien! Entonces, eres ${userAdj}. ¿Qué te gusta hacer en tu tiempo libre?`);
        step++;
      } else if (step === 4) {
        await respond(`¡Gracias por compartir, ${userName}! Encantado de conocerte. ¡Hasta luego!`);
        step++;
      } else {
        await respond("Recarga la página para practicar de nuevo. 😊");
      }
    }

    sendBtn.addEventListener('click', async () => {
      const userText = input.value.trim();
      if (!userText) return;
      addMessage(userText, 'user');
      await handleResponse(userText);
      input.value = '';
      input.focus();
    });

    input.addEventListener('keydown', e => {
      if (e.key === 'Enter') sendBtn.click();
    });

    // Only one accent selector, but keep for extensibility
    flags.forEach(btn => {
      btn.addEventListener('click', async () => {
        flags.forEach(b => b.classList.remove('selected'));
        btn.classList.add('selected');
        selectedAccent = btn.dataset.accent;
        await selectVoice();
        if (recognition) recognition.lang = selectedAccent;
      });
    });

    // Speech recognition setup
    let recognition;
    if ('webkitSpeechRecognition' in window) {
      recognition = new webkitSpeechRecognition();
      recognition.lang = selectedAccent;
      recognition.continuous = false;
      recognition.interimResults = false;

      recognition.onresult = e => {
        input.value = e.results[0][0].transcript;
        sendBtn.click();
      };
    } else {
      micBtn.disabled = true;
      micBtn.title = "El reconocimiento de voz no está soportado.";
    }

    micBtn.addEventListener('click', () => {
      if (recognition) recognition.start();
    });

    // Ensure voices are loaded and selected before starting
    window.onload = async () => {
      await selectVoice();
      await respond("¡Hola! Soy Atlas. ¿Cómo te llamas?");
      input.focus();
    };

    // Also re-select voice if voices list changes (e.g. after voices load)
    if ('speechSynthesis' in window) {
      speechSynthesis.onvoiceschanged = selectVoice;
    }
  </script>
</body>
</html>
