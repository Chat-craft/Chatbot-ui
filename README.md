# Chat‑Craft UI – Chatbot Front‑End

![Chat‑Craft](https://img.shields.io/badge/Chat--Craft-CaaS-blue?style=flat-square)  ![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

> **Chat‑Craft** is a *Chatbot‑as‑a‑Service (CaaS)* platform that bridges the information gap inside organisations by delivering secure, scalable and intelligent Retrieval‑Augmented Generation (RAG) over internal knowledge bases. This repository hosts the **front‑end chatbot UI** and the **iframe export** that lets you embed a fully‑featured conversational assistant into any page with a single HTML tag.

---

## ✨ Key Features

| Feature                            | Description                                                                                                    |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Conversational UI**              | React‑based chat experience with rich‑text, code and markdown rendering.                                       |
| **Retrieval‑Augmented Generation** | Combines semantic search with LLMs to provide context‑aware answers from your documents.                       |
| **Secure, Org‑Scoped Data Access** | All queries are scoped to your company’s index; no data leaves your tenancy.                                   |
| **Plug‑and‑Play Embed**            | Drop an `<iframe>` tag anywhere (Confluence, Notion, intranet, external site) to bring Chat‑Craft to the user. |
| **Themeable & Extensible**         | Dark/light mode, custom CSS variables and component overrides.                                                 |
| **Analytics Hooks**                | Emit custom events to the parent window for usage tracking.                                                    |

---

## 🛠 Tech Stack

* **React 18** with **TypeScript**
* **Vite** build tooling
* **Tailwind CSS** for utility‑first styling
* **Headless UI** + **Radix Primitives** for accessibility
* **Socket.io** (optional) for real‑time streaming tokens

> *This repo focuses solely on the client. The backend (vector storage, LLM orchestration, auth) lives in `Chat‑Craft/server`.*

---

## 🚀 Getting Started

### Prerequisites

|  Tool       | Version                        |
| ----------- | ------------------------------ |
| **Node.js** | ≥ 18 .x                        |
| **npm**     | ≥ 9 .x (or **pnpm**/ **yarn**) |

### Installation

```bash
# 1 — Clone the repo
$ git clone https://github.com/your‑org/chat‑craft‑ui.git
$ cd chat‑craft‑ui

# 2 — Install dependencies
$ npm install

# 3 — Configure env variables
$ cp .env.example .env
$ $EDITOR .env  # fill VITE_API_URL, VITE_AUTH_TOKEN, etc.

# 4 — Run locally
$ npm run dev

# 5 — Build for production
$ npm run build && npm run preview
```

---

## 📦 Embedding the Chatbot

The build pipeline produces a **zero‑dependency iframe bundle** located in `dist/embed`. To drop the chatbot into any web page, copy‑paste the snippet below:

```html
<!-- Chat‑Craft Embed -->
<iframe
  src="https://cdn.your‑org.com/chat‑craft/embed.html?orgId=ACME&theme=dark"
  title="Chat‑Craft Assistant"
  style="width:100%; height:680px; border:none; border-radius:12px; overflow:hidden;"
  loading="lazy"
  referrerpolicy="no-referrer"
></iframe>
```

| Query Param | Purpose                                                 |
| ----------- | ------------------------------------------------------- |
| `orgId`     | Matches the tenant in the backend (required)            |
| `userId`    | Pre‑fills the session with SSO identity (optional)      |
| `theme`     | `light`, `dark` or a custom CSS‑vars palette (optional) |
| `lang`      | UI locale (e.g. `en`, `fr`, `ja`)                       |

> Need fine‑grained control? Import `@chat‑craft/sdk` instead and mount the `<ChatCraftProvider>` directly in your SPA.

---

## 🔧 Configuration

|  Variable                      | Description                                   |
| ------------------------------ | --------------------------------------------- |
| `VITE_API_URL`                 | Base URL of the Chat‑Craft backend gateway    |
| `VITE_AUTH_TOKEN`              | JWT or API token issued by your IdP           |
| `VITE_IFRAME_ORIGIN_WHITELIST` | Comma‑separated list of allowed embed domains |

See `.env.example` for the full list.

---

## 🗂 Folder Structure

```
chat‑craft‑ui/
├── public/            # Icons, manifest, og‑images
├── src/
│   ├── assets/        # Static assets (SVG, images)
│   ├── components/    # Reusable UI primitives
│   ├── hooks/         # Custom React hooks
│   ├── pages/         # Route‑level views (if using React Router)
│   ├── utils/         # Helper libs (tokenizer, markdown‑to‑AST)
│   └── index.tsx      # Vite entry point
└── vite.config.ts     # Build config
```

---

## 🧑‍💻 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feat/amazing‑feature`)
3. Commit your changes (`git commit -am 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feat/amazing‑feature`)
5. Open a Pull Request

All PRs require at least one approval and a passing CI.

---

## 🙌 Authors

| Role                                  | Name                    |
| ------------------------------------- | ----------------------- |
| **Chatbot Front‑End & IFrame Export** | **@your‑github‑handle** |
| Platform & Backend                    | Chat‑Craft Core Team    |

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 📣 Acknowledgements

* [OpenAI API](https://openai.com)
* [LangChain](https://github.com/langchain-ai)
* \[Vector DB of your choice] – Pinecone, Weaviate, Qdrant…
* [Vercel](https://vercel.com) for CDN‑edge hosting

> Have questions or feedback? Reach us at **support\@chat‑craft.io** or open an issue.




# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
