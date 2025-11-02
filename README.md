# Layr - AI Planning Layer

**Transform your ideas into structured project plans with AI-powered planning for VS Code.**

Layr is a VS Code extension that generates comprehensive, actionable project plans from natural language descriptions. Whether you're starting a new project or planning a feature, Layr helps you think through the architecture, requirements, and implementation steps before you write the first line of code.

## Demo Video

[Watch the demo video](https://youtu.be/9xtDDoh-Fg8)


## Key Benefits

**Intelligent Planning** : Leverages Google's Gemini AI to create detailed, context-aware project plans tailored to your specific requirements.

**Zero Setup Required** : Works immediately with built-in templates. No API key needed for basic functionality.

**Seamless Integration** : Native VS Code integration through Command Palette with instant access to planning tools.

**Flexible Output** : Generates editable Markdown documents that you can customize and reference throughout development.

**Smart Fallback** : Automatically switches to offline template mode if AI service is unavailable.

**Secure Configuration** : Multiple options for API key storage with built-in security best practices.

## Installation

### From VS Code Marketplace
1. Open VS Code
2. Go to Extensions (Ctrl+Shift+X)
3. Search for "Layr"
4. Click Install

### From Source
1. Clone this repository
2. Open in VS Code
3. Run `npm install`
4. Press F5 to launch in Extension Development Host

## Configuration

### AI-Powered Plans 

Layr now supports multiple AI providers! Choose from Gemini, OpenAI, or Claude to generate your project plans.

**Step 1: Choose Your AI Provider**
1. Open VS Code Settings (Ctrl+,)
2. Search for "layr"
3. Set "AI Provider" to your preferred option:
   - `gemini` (default) - Google's Gemini AI
   - `openai` - OpenAI's GPT models
   - `claude` - Anthropic's Claude models

**Step 2: Configure API Key**

**For Gemini:**
1. Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Enter your API key in the "Gemini Api Key" field

**For OpenAI:**
1. Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)
2. Enter your API key in the "OpenAI Api Key" field
3. Optionally set your organization ID in "OpenAI Organization"

**For Claude:**
1. Get your API key from [Anthropic Console](https://console.anthropic.com/)
2. Enter your API key in the "Claude Api Key" field

**Step 3: Choose Model (Optional)**
- Gemini Model: `gemini-pro` (default) or `gemini-pro-vision`
- OpenAI Model: `gpt-4` (default), `gpt-4-turbo`, or `gpt-3.5-turbo`
- Claude Model: `claude-3-sonnet` (default), `claude-3-opus`, or `claude-3-haiku`

**Alternative: Environment Variables**
Add to your `.env` file or system environment:
```bash
# Choose one or more based on your preferred provider
GEMINI_API_KEY=your_gemini_api_key_here
OPENAI_API_KEY=your_openai_api_key_here
CLAUDE_API_KEY=your_claude_api_key_here
```

**Security Note** : API keys are stored locally and never transmitted except to the respective AI provider's API. The extension is configured to prevent accidental commits of sensitive information.

## Usage Guide

### Creating a Plan

1. **Open Command Palette** : Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
2. **Run Command** : Type "Layr: Create Plan" and press Enter
3. **Describe Your Project** : Enter a natural language description of what you want to build
   - Example: "A React todo app with user authentication and real-time updates"
   - Example: "A REST API for a blog platform with user management"
   - Example: "A Python data analysis script for sales reporting"
4. **Review Generated Plan** : The extension will create a new Markdown file with your project plan
5. **Customize as Needed** : Edit the generated plan to match your specific requirements

### Best Practices for Prompts

**Be Specific** : Include technology preferences, key features, and constraints
- Good: "A Node.js REST API with JWT authentication, PostgreSQL database, and Docker deployment"
- Basic: "A web API"

**Mention Context** : Include information about scale, audience, or special requirements
- "A mobile-first React app for small businesses with offline capability"
- "A Python script for processing large CSV files with memory optimization"

**Include Constraints** : Mention any limitations or preferences
- "Using only free/open-source technologies"
- "Must be deployable on AWS Lambda"

## Available Commands

| Command | Description | Shortcut |
|---------|-------------|----------|
| `Layr: Create Plan` | Generate a new project plan from description | None |
| `Layr: Execute Plan` | Execute current plan (coming soon) | None |

## Plan Output Structure

Generated plans include:

**Project Overview** : High-level description and objectives
**Requirements** : Functional and technical requirements
**Architecture** : System design and component structure
**Technology Stack** : Recommended tools and frameworks
**Implementation Steps** : Detailed development phases
**File Structure** : Suggested project organization
**Testing Strategy** : Approach for quality assurance
**Deployment**  : Production deployment considerations

## AI vs Template Mode

### AI Mode (Gemini)
**Advantages** :
- Highly customized plans based on your specific description
- Considers modern best practices and current technologies
- Adapts to complex or unique project requirements
- Provides detailed explanations and rationale

**Requirements** :
- Internet connection
- Valid Gemini API key
- Google AI Studio account

**Best For** : Complex projects, modern tech stacks, unique requirements

### Template Mode (Offline - currently on testing)
**Advantages** :
- Works without internet connection
- No API key required
- Instant generation
- Consistent structure

**Limitations** :
- Limited to predefined project types
- Less customization
- May not reflect latest technologies

**Best For** : Common project patterns, quick prototyping, offline development

## Troubleshooting

### Common Issues

**"Failed to generate plan"**
- Check internet connection
- Verify API key is correctly configured
- Try using template mode as fallback

**"API key not found"**
- Ensure API key is set in VS Code settings
- Check that the key is valid and active
- Verify the key has appropriate permissions

**"Extension not responding"**
- Reload VS Code window (Ctrl+Shift+P → "Developer: Reload Window")
- Check VS Code output panel for error messages
- Ensure extension is properly installed and enabled

### Getting Help

- Check the [GitHub repository](https://github.com/manasdutta04/layr) for known issues
- Review VS Code's extension troubleshooting guide
- Submit bug reports with detailed error messages and steps to reproduce

## Privacy and Security

- API keys are stored locally in VS Code settings
- No data is collected or transmitted except to Google's Gemini API
- Generated plans remain on your local machine
- All communication with external services uses secure HTTPS connections

## Contributing

Contributions are welcome! Please see the repository for development setup instructions and contribution guidelines.

## License

This project is licensed under the MIT License. See the LICENSE file for details.


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
- Built with [VS Code Extension API](https://code.visualstudio.com/api)

## Issues & Support

If you encounter any issues or have suggestions:
1. Check existing issues on GitHub
2. Create a new issue with detailed description
3. Include VS Code version and extension logs
