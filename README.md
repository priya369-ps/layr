# Layr - AI Planning Layer for VS Code

 **A "planning layer" that uses AI to generate intelligent project plans from natural language prompts.**

Layr helps you plan before you code by generating structured, actionable project plans that you can edit and follow step-by-step.

##  Features

- 1. AI-Powered Planning: Uses Google's Gemini AI to generate intelligent, detailed project plans
- 2. Offline Mode: Works without an API key using built-in rule-based templates
- 3. Markdown Output: Plans are generated as editable Markdown documents
- 4. Command Palette Integration: Easy access through VS Code's command palette
- 5. Flexible Configuration: Store API key in settings or environment variables
- 6. Smart Fallback: Automatically falls back to offline mode if AI service fails

##  Quick Start

### 1. Installation

1. Clone this repository
2. Open in VS Code
3. Run `npm install` to install dependencies
4. Press `F5` to launch the extension in a new Extension Development Host window

### 2. Configuration (Optional)

For AI-powered plans, configure your Gemini API key:

**Option A: VS Code Settings (Recommended)**
1. Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Open VS Code Settings (`Ctrl+,`)
3. Search for "layr"
4. Enter your Gemini API key in the "Gemini Api Key" field

**Option B: VS Code Settings File**
1. Copy `.vscode/settings.example.json` to `.vscode/settings.json`
2. Replace `YOUR_GEMINI_API_KEY_HERE` with your actual API key
3. The settings.json file is automatically ignored by git for security

**Option C: Environment Variable**
1. Add to your `.env` file:
   ```
   GEMINI_API_KEY=your_api_key_here
   ```

⚠️ **Security Note**: Never commit API keys to version control. The extension is configured to keep your API key secure.

### 3. Usage

1. Open the Command Palette (`Ctrl+Shift+P`)
2. Type "Layr: Create Plan"
3. Enter what you want to build (e.g., "A React todo app with authentication")
4. Wait for the plan to generate
5. Edit and follow the generated plan!

##  Commands

| Command | Description |
|---------|-------------|
| `Layr: Create Plan` | Generate a new project plan from your description |
| `Layr: Execute Plan` | Execute the current plan (coming soon!) |

##  Project Structure

```
layr/
├── src/
│   ├── extension.ts           # Main extension entry point
│   └── planner/
│       ├── index.ts          # Main planner orchestrator
│       ├── ai.ts             # Gemini AI integration
│       ├── rules.ts          # Offline template system
│       └── interfaces.ts     # TypeScript interfaces
├── .vscode/
│   ├── launch.json           # Debug configuration
│   └── tasks.json            # Build tasks
├── package.json              # Extension manifest
├── tsconfig.json             # TypeScript configuration
├── .env                      # Environment variables
└── README.md                 # This file
```

## AI vs Offline Mode

### AI Mode (Gemini)
- **Pros**: Intelligent, context-aware plans tailored to your specific request
- **Cons**: Requires API key and internet connection
- **Best for**: Complex, unique projects that need custom planning

### Offline Mode (Templates)
- **Pros**: Works anywhere, no setup required, instant generation
- **Cons**: Limited to predefined templates
- **Best for**: Common project types (web apps, APIs, mobile apps)

## Example Plan Output

```markdown
# React Todo App with Authentication - Web Application Project

*Generated on 12/28/2024 at 2:30:15 PM using Gemini AI*

## Overview
A modern web application with responsive design and interactive features. This plan was generated based on your request: "A React todo app with authentication"

## Requirements
- User authentication (login/register)
- Todo CRUD operations
- Responsive design for mobile and desktop
- Modern JavaScript framework (React)
- State management (Redux/Context)
- Backend API integration
- Testing framework (Jest)

## File Structure
```
📁 src/
  📁 components/
    📄 TodoList.jsx
    📄 TodoItem.jsx
    📄 AuthForm.jsx
  📁 pages/
    📄 Dashboard.jsx
    📄 Login.jsx
  📄 App.jsx
📄 package.json
📄 README.md
```


##  Development

### Prerequisites
- Node.js 16+
- VS Code
- TypeScript knowledge

### Setup
```bash
# Install dependencies
npm install

# Compile TypeScript
npm run compile

# Watch for changes
npm run watch

# Debug in VS Code
# Press F5 to launch Extension Development Host
```

### Building
```bash
# Compile for production
npm run vscode:prepublish
```

##  Configuration Options

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `layr.geminiApiKey` | string | `""` | Your Gemini AI API key for generating intelligent plans |

##  Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

##  License

MIT License - see LICENSE file for details

##  Acknowledgments

- Developed by [Manas Dutta](https://github.com/manasdutta04)
- Inspired by [Traycer](https://traycer.com/) - the planning-first approach to development
- Powered by [Google Gemini AI](https://ai.google.dev/)
- Built with [VS Code Extension API](https://code.visualstudio.com/api)

## Issues & Support

If you encounter any issues or have suggestions:
1. Check existing issues on GitHub
2. Create a new issue with detailed description
3. Include VS Code version and extension logs
