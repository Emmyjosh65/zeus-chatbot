# 🧠 ZEUS ChatBot

A modern ChatGPT-like chatbot built on **Nuxt 4** with **OpenAI API** integration.

## 🚀 Features

✅ **Real-time Streaming Chat** - Get instant AI responses  
✅ **Conversation History** - Keep track of all messages  
✅ **Modern UI** - Beautiful gradient design with smooth animations  
✅ **Responsive Design** - Works on desktop and mobile  
✅ **Error Handling** - Graceful error messages  
✅ **Type-Safe** - Built with TypeScript  
✅ **Full-Stack** - Nuxt with Nitro backend  

## 📁 Project Structure

```
playground/
├── components/
│   └── ChatBot.vue          # Main chatbot UI component
├── composables/
│   └── useChat.ts           # Chat state management composable
├── server/
│   └── api/
│       └── chat.ts          # OpenAI API endpoint with streaming
├── app.vue                  # Root component
├── nuxt.config.ts           # Nuxt configuration
├── .env.example             # Environment variables template
└── package.json             # Dependencies
```

## 🔧 Setup Instructions

### 1. Get OpenAI API Key

1. Go to [OpenAI Platform](https://platform.openai.com)
2. Sign up or log in
3. Navigate to API keys section
4. Create a new API key
5. Copy the key (save it securely)

### 2. Configure Environment

```bash
cd playground
cp .env.example .env
```

Then edit `.env` and add your OpenAI API key:

```env
OPENAI_API_KEY=sk-your-api-key-here
```

### 3. Install Dependencies

```bash
# From root directory
pnpm install

# Or if using npm
npm install
```

### 4. Run the Development Server

```bash
# From root directory
pnpm play

# Or from playground directory
cd playground
npm run dev
```

The chatbot will be available at: `http://localhost:3000`

## 📝 Usage

1. **Type your message** in the input field
2. **Press Enter** or click the **Send** button
3. **Wait for AI response** - The bot will stream the answer in real-time
4. **Continue the conversation** - Your chat history is maintained
5. **Clear chat** - Click the Clear Chat button to start fresh

## 🔌 API Endpoints

### POST `/api/chat`

Sends a message and streams the AI response.

**Request:**
```json
{
  "messages": [
    {
      "role": "user",
      "content": "Hello, how are you?"
    }
  ],
  "model": "gpt-3.5-turbo",
  "temperature": 0.7
}
```

**Response:** Server-Sent Events (SSE) stream

```
data: {"content": "I'm doing great"}
data: {"content": ", thank you"}
data: {"content": " for asking"}
```

## 🎯 How It Works

1. **Frontend**: Vue component captures user input
2. **Composable**: `useChat` manages state and API calls
3. **Backend**: Nitro server endpoint (`/api/chat`) forwards requests to OpenAI
4. **Streaming**: Server-sent events stream the response in real-time
5. **UI Update**: Vue reactivity updates the UI as chunks arrive

## 🛠️ Technologies Used

- **Nuxt 4** - Full-stack Vue framework
- **Vue 3** - Component framework
- **TypeScript** - Type safety
- **Nitro** - Backend server
- **OpenAI API** - AI responses
- **Server-Sent Events (SSE)** - Real-time streaming

## 🔐 Security Notes

- **Never commit `.env` files** - Add to `.gitignore`
- **Keep API keys secret** - Use environment variables
- **Rate limiting** - Consider implementing rate limits for production
- **Input validation** - Messages are validated on the backend

## 📦 Dependencies

Main dependencies installed in `playground/package.json`:
- `nuxt` - Framework
- `vue` - Component library
- No additional npm packages needed for core functionality

## 🚀 Deployment

### Deploy to Vercel

```bash
pnpm dlx nuxi deploy playground
```

### Deploy to Netlify

```bash
pnpm build:nuxt-playground
```

**Environment Variables on Production:**
- Set `OPENAI_API_KEY` in your deployment platform's environment variables

## 🐛 Troubleshooting

**Issue: "OpenAI API key not configured"**
- Make sure `.env` file exists
- Check `OPENAI_API_KEY` is set correctly
- Verify no typos in the key

**Issue: "Failed to get response"**
- Check your OpenAI API key is valid
- Ensure you have API credits
- Check OpenAI API status

**Issue: Messages not streaming**
- Verify browser supports Server-Sent Events
- Check network tab for response headers
- Try in a different browser

## 📚 Resources

- [Nuxt Documentation](https://nuxt.com)
- [OpenAI API Docs](https://platform.openai.com/docs)
- [Vue 3 Guide](https://vuejs.org)
- [Nitro Documentation](https://nitro.unjs.io)

## 📄 License

MIT - See LICENSE in root directory

## 🤝 Contributing

Contributions are welcome! Feel free to submit pull requests or open issues.

---

**Built with ❤️ using Nuxt and OpenAI**
