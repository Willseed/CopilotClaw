# Copilot Instructions for telegram-copilot-bot

## Project Overview
This is a Telegram bot that integrates with GitHub Copilot CLI. The bot entry point is `src/index.ts`, shared utilities are in `src/utils.ts`, and Jest tests live in `tests/`. Compiled output goes to `dist/` (don't edit manually).

## Project Structure
- `src/` - TypeScript source code
  - `index.ts` - Main bot entry point
  - `utils.ts` - Shared helper functions
- `tests/` - Jest unit tests (*.test.ts)
- `dist/` - Compiled JavaScript output (auto-generated)
- `directories.json` - Configuration defaults
- `.env` - Local secrets (never commit)

## Development Workflow
```sh
npm install            # Install dependencies
npm run build          # Compile TypeScript to dist/
npm run dev            # Run with ts-node (development)
npm start              # Build and run production
npm test               # Run Jest test suite
npm run test:coverage  # Run tests with coverage
```

**Requirements**: Node.js 18+

## Code Style
- Language: TypeScript with `strict` mode and ESM modules
- Indentation: 2 spaces
- Strings: Single quotes
- Naming:
  - camelCase for variables and functions
  - PascalCase for types and interfaces
  - Descriptive filenames (e.g., `utils.ts`)
- Test files: `*.test.ts` in `tests/` directory

## Testing Requirements
- Use Jest + ts-jest (configured in `jest.config.js`)
- Add/update tests when changing:
  - Command parsing logic
  - Session lifecycle handling
  - Utility helpers
- Keep tests focused and isolated
- Mock Telegram/Copilot integrations to avoid external dependencies

## Commit Guidelines
Follow Conventional Commits 1.0.0 format with optional scopes:
- `feat: add new feature`
- `fix(bot): fix telegram command parsing`
- `docs(README): update setup instructions`
- `test: add session lifecycle tests`

**Commit message format** (in Traditional Chinese):
```
type(scope): subject

變更原因：
- [explain why the change was made]

行為影響：
- [describe behavior changes]

測試結果：
- [list tests run or explain why not]
```

## Pull Request Guidelines
Include in PR description:
- Short summary of changes
- Tests run (or explanation if not)
- New environment variables or config changes
- For user-facing changes: example bot output or chat flow screenshot

## Security & Configuration
- Store secrets in `.env` (never commit):
  - `TELEGRAM_BOT_TOKEN`
  - `DIRECTORY_PATTERNS`
  - `COPILOT_MODEL`
- Ensure GitHub Copilot CLI is installed and available on `PATH`

## When Writing Code
1. Use TypeScript strict mode features
2. Keep functions small and focused
3. Add JSDoc comments for public APIs
4. Handle errors gracefully
5. Write tests for new functionality
6. Update documentation if needed

## When Preparing Commits
Generate commit message in Traditional Chinese following the format above, but **do not execute** `git commit` - only output the suggested message.
