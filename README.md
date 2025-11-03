## 🧮 MCP Calculator Server — Build Your First MCP Tool with TypeScript

A lightweight **Model Context Protocol (MCP) server** built in **TypeScript** using the official `@modelcontextprotocol/sdk`.
This server exposes a simple tool that performs **addition of two numbers**, showcasing how to build custom MCP-compatible tools.

---

### 🚀 Features

* Built using the official **MCP SDK**
* Implements a simple calculator with an `add` function
* Written in **TypeScript**
* Easy to extend for new MCP tools

---

### 📁 Project Structure

```
my-calculator/
│
├── src/
│   └── index.ts          # Main server logic
├── package.json
├── tsconfig.json
└── README.md
```

---

### ⚙️ Setup Instructions

#### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/mcp-calculator-server.git
cd mcp-calculator-server
```

#### 2. Install Dependencies

Make sure you have **Node.js (v18+)** and **npm** installed.

```bash
npm install
```

#### 3. Build the Project

```bash
npm run build
```

#### 4. Start the MCP Server

```bash
npm run start
```

You should see:

```
✅ MCP Calculator Server is running...
```

---

### 🧠 How It Works

The project uses `@modelcontextprotocol/sdk` to create a minimal MCP server.

```ts
import { server } from "@modelcontextprotocol/sdk/server/stdio";
import { z } from "zod";

const s = server({
  name: "MCP Calculator Server",
});

s.tool(
  "add",
  {
    a: z.number(),
    b: z.number(),
  },
  async ({ a, b }) => ({
    content: [{ type: "text", text: `Result: ${a + b}` }],
  })
);

s.start();
console.log("✅ MCP Calculator Server is running...");
```

This registers an `add` tool, which takes two numbers (`a`, `b`) and returns their sum.

---

### 🧩 Testing (Optional)

If you want to test manually:

```bash
npm run start
```

Then, you can connect this server to any **MCP-compatible client** (like **Claude Desktop**, **ChatGPT with MCP**, or other integrations).

---

### 🧱 Build Commands Reference

| Command         | Description                         |
| --------------- | ----------------------------------- |
| `npm run build` | Compiles TypeScript into JavaScript |
| `npm run start` | Starts the MCP server with ts-node  |
| `npm install`   | Installs all dependencies           |

---

### 🧰 Tech Stack

* **TypeScript**
* **Node.js**
* **Model Context Protocol SDK**
* **Zod (Schema validation)**

---

### 📜 License

MIT License — feel free to fork and modify.



