# Quint Studio

The integrated development environment (IDE) for QUINT-YourOS.

## Features

- **Code Editor**: Syntax highlighting, auto-completion, error detection
- **AI Assistant**: In-IDE AI support for code generation and suggestions
- **Project Manager**: Organize files and dependencies
- **Debugger**: Step through code, inspect variables, set breakpoints
- **Terminal**: Integrated command-line interface
- **File Explorer**: Navigate project structure
- **Testing Panel**: Run and view test results
- **Marketplace**: Browse and install extensions
- **Settings**: Customize environment

## UI Components

```
┌─────────────────────────────────────┐
│     Quint Studio                    │
├──────────────┬──────────────────────┤
│              │                      │
│ File         │  Code Editor         │
│ Explorer     │                      │
│              │                      │
│              ├──────────────────────┤
│              │ AI Assistant Panel   │
├──────────────┼──────────────────────┤
│  Terminal / Testing / Output        │
└──────────────┴──────────────────────┘
```

## Project Structure

```
quint-studio/
├── src/
│   ├── components/      # React components
│   ├── editors/         # Code editor
│   ├── panels/          # UI panels
│   ├── services/        # API services
│   └── App.tsx
├── public/
└── package.json
```

## Development

### Installation

```bash
npm install
```

### Running Development Server

```bash
npm run dev
```

### Building

```bash
npm run build
```

## Technology Stack

- React 18+
- TypeScript
- Vite
- Monaco Editor
- Tailwind CSS

## Status

- [ ] Basic UI layout
- [ ] Code editor integration
- [ ] File explorer
- [ ] Terminal
- [ ] AI assistant panel
- [ ] Debugging features
- [ ] Settings panel
