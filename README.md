# 🧠 Chatbot IUT
**Chatbot vocal intelligent basé sur Whisper, LightRAG et Ollama**

---

🖼️ Des captures d’écran explicatives sont disponibles sur : [lgelgon.fr/PageChatbot](https://lgelgon.fr/PageChatbot)

---

## 🎯 Objectif  
Créer un chatbot vocal capable de :
- **Comprendre une question orale** même mal formulée (grâce à Whisper)
- **Extraire la réponse à partir de documents internes** (grâce à LightRAG + Ollama)
- **Afficher une réponse complète et structurée**  

---

## 📦 Dépendances

- `Python 3.10+`
- `whisper` (transcription audio)
- `LightRAG` (moteur RAG simplifié)
- `Ollama` (modèle LLM local : gemma2:2b)
- `nomic-embed-text` (embedding des documents)
- `TTS` (optionnel, génération audio)

---

## ⚙️ Exigences

- Ollama installé localement et démarré (`ollama start`)
- Modèles téléchargés :
  ```bash
  ollama pull gemma2:2b
  ollama pull nomic-embed-text
  ```
- Un dossier `audio/` contenant :
  - `audio_mauvais.mp3`
  - `audio_confus.mp3`
  - `audio_clair.mp3`

---

## 🧪 Fonctionnement

1. **L’utilisateur pose une question à l’oral** → audio enregistré
2. **Whisper transcrit l’audio** en texte
3. **LightRAG** interroge une base documentaire (informations sur l’IUT de Vannes)
4. **La réponse est générée** sous forme de texte et audio

---

## 🔍 Contenu des scénarios testés

| Configuration | Niveau de clarté | Résultat LLM |
|---------------|------------------|------------------|
| Mauvaise      | Bruit, voix peu distincte | Réponse vague ou incomplète |
| Moyenne       | Question floue   | Réponse partielle mais correcte |
| Bonne         | Question claire  | Réponse complète, structurée |

---

## 📁 Structure du projet

```
📦 iut_chatbot/
 ┣ audio/
 ┃ ┣ audio_mauvais.mp3
 ┃ ┣ audio_confus.mp3
 ┃ ┗ audio_clair.mp3
 ┣ speaker_x.wav (optionnel)
 ┣ whisper_transcriber.py
 ┣ rag_query.py
 ┣ voice_generator.py (optionnel)
 ┗ main.py
```

---

## 👨‍💻 Auteur

Lucas Gelgon  
