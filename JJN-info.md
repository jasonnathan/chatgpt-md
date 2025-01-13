# JJN-INFO: CHATGPT-MD

## Purpose
`CHATGPT-MD` integrates ChatGPT into Obsidian, enabling conversational workflows directly from Markdown files. It provides features to create, manage, and interact with ChatGPT-driven chats seamlessly within the Obsidian environment, leveraging frontmatter configurations and Markdown formatting.

## Key Features
- **Chat Integration**: Directly chat with ChatGPT from any Markdown note.
- **Chat Templates**: Use reusable templates to standardize and simplify interactions.
- **Frontmatter Configuration**: Customize API parameters like `max_tokens` or `model` via frontmatter.
- **Streaming Responses**: Real-time character streaming for a responsive experience.
- **Highlight & Chat**: Generate new chats from selected text in a note.
- **Infer Titles**: Automatically generate chat titles after 4+ messages.
- **Comment Blocks**: Add notes or backlinks that are ignored during processing.
- **Command Palette**: Supports commands like creating new chats, clearing messages, or stopping streams.

## Installation
1. **Community Plugins**:
   - Search for `CHATGPT-MD` in Obsidian's Community Plugins section.
2. **Local Installation**:
   - Clone the repository to the `plugins` directory.
   - Run `npm i` followed by `npm run build`.

## File Structure
- **Core Files**:
  - `main.ts`: Entry point of the plugin, defines the main functionality and lifecycle hooks.
  - `helpers.ts`: Utility functions supporting various operations.
  - `stream.ts`: Manages real-time streaming of ChatGPT responses into Obsidian.
  - `version-bump.mjs`: Automates version updates.
- **Configuration and Metadata**:
  - `manifest.json`: Plugin metadata for Obsidian.
  - `versions.json`: Version history tracking.
  - `tsconfig.json`: TypeScript configuration for the project.
- **Assets**:
  - `video-thumbnail.png`: Thumbnail for demo videos.
- **Build Tools**:
  - `esbuild.config.mjs`: Defines build steps using `esbuild`.
- **License**:
  - `LICENSE`: MIT License.

## Workflow
1. **Chat Initialization**:
   - A divider (`<hr class="__chatgpt_plugin">`) and `role` metadata (`system`, `assistant`, `user`) are required for the plugin to function.
   - Frontmatter customizations allow tailored interactions (e.g., model, tokens, and API keys).
2. **Streaming**:
   - Streams responses character-by-character, either at the cursor position or the end of the file.
3. **Chat Templates**:
   - Users can create reusable templates stored in a designated folder.
4. **Commands**:
   - Commands include chat creation, infer titles, add comment blocks, clear chats, and stop streaming.
5. **File Structure in Obsidian**:
   - Chats are stored in a designated folder. Templates are stored separately.

## Commands
- **Chat**: Initiates a chat from the current file.
- **Create Chat from Highlight**: Generates a chat from selected text.
- **Create Chat from Template**: Uses a template to create a new chat file.
- **Infer Title**: Automatically generates a title from chat messages.
- **Add Comment Block**: Inserts a non-processable comment block.
- **Clear Chat**: Removes messages but retains the frontmatter.
- **Stop Streaming**: Halts the response stream.

## Technical Highlights
- **Dependencies**:
  - `esbuild`: Handles bundling and builds.
  - `typescript`: Provides type safety.
  - `obsidian`: Ensures compatibility with the Obsidian API.
  - `sse`: Manages server-sent events for streaming.
- **Integration Points**:
  - Frontmatter variables allow API configuration.
  - Markdown rendering supports complex layouts like code blocks and lists.

## Known Issues
- **Cut-off Responses**: Increase `max_tokens` in frontmatter if responses truncate prematurely.
- **Code Block Rendering**: Extra backticks may appear due to Obsidian’s rendering logic; users need to manually handle these.

## Notes
- The project has both an upstream (`bramses/chatgpt-md`) and an origin (`jasonnathan/chatgpt-md`) repository.
- A call for new maintainers was posted in April 2024. The original developer is Bram Adams, an experienced programmer and AI advocate.

## Potential Improvements
- Enhance compatibility with Obsidian’s mobile app.
- Add support for additional LLM providers.
- Improve streaming performance for larger token responses.
- Introduce localized language support for better infer title capabilities.

