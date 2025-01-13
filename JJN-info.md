# JJN-INFO: CHATGPT-MD

## Purpose
`CHATGPT-MD` is a plugin that integrates ChatGPT functionality into Obsidian, offering users an enhanced, conversational workflow directly within Markdown notes. It leverages frontmatter configurations, Markdown structures, and Obsidian commands to provide a seamless integration for creating, managing, and interacting with ChatGPT-driven chats.

## Features
- **Chat from Any Note**: Initiate a conversation directly from any Markdown file.
- **Chat Templates**: Use predefined templates stored in a `Chat Template Folder` for standardized conversations.
- **Minimal Boilerplate**: Requires only `<hr class="__chatgpt_plugin">` and `role::system|assistant|user` for functionality.
- **Frontmatter Configuration**: Customize settings such as `max_tokens`, `model`, and API endpoints via YAML frontmatter.
- **Streaming Responses**: Displays ChatGPT responses in real-time as characters are received.
- **Highlighted Text Chat**: Create a new chat using highlighted text in an existing note.
- **Infer Titles**: Automatically generate titles for chats after 4+ messages.
- **Custom Endpoints**: Allows API endpoint customization for non-OpenAI hosted services.
- **Comment Blocks**: Insert non-processed blocks in notes, starting with `=begin-chatgpt-md-comment` and ending with `=end-chatgpt-md-comment`.
- **Commands**: Includes commands for creating chats, clearing chats, stopping streams, and more.

## Installation
1. **Community Plugin**:
   - Search for `CHATGPT-MD` in Obsidian's Community Plugins section.
2. **Local Installation**:
   - Clone the repository into the Obsidian `plugins` directory.
   - Run `npm i` and `npm run build`.
3. **Configuration**:
   - Insert the OpenAI API key in the plugin settings.
   - Define `Chat Folder` and `Chat Template Folder`.
   - Add a hotkey for `Chat` (e.g., `alt-[`).

## Workflow
1. **Core Interaction**:
   - Each chat requires a divider (`<hr class="__chatgpt_plugin">`) and a role declaration (`role::system|assistant|user`) in the note.
2. **Streaming**:
   - Responses are streamed in real-time at either the cursor position or the end of the file, as configured.
3. **Templates**:
   - Templates are stored in a dedicated folder and can be used to quickly initiate standardized conversations.
4. **Commands**:
   - Various commands allow initiating chats, inferring titles, adding comment blocks, clearing chats, and stopping streams.

## File Structure
- **Core Files**:
  - `main.ts`: Entry point for the plugin’s functionality.
  - `helpers.ts`: Utility functions for processing.
  - `stream.ts`: Manages real-time response streaming.
  - `version-bump.mjs`: Handles automated versioning.
- **Configuration Files**:
  - `manifest.json`: Metadata for plugin compatibility with Obsidian.
  - `versions.json`: Tracks version history.
  - `tsconfig.json`: TypeScript configuration.
- **Assets**:
  - `video-thumbnail.png`: Demo thumbnail for video links.
- **Build Tools**:
  - `esbuild.config.mjs`: Configures the `esbuild` bundler.

## Known Issues
- **Truncated Responses**: Increase `max_tokens` in frontmatter if responses are cut off.
- **Extra Backticks in Code Blocks**: Addressed by manually closing blocks before the `<hr>`.

## Dependencies
- **Development**:
  - `esbuild`: Bundler for efficient builds.
  - `typescript`: Provides type safety during development.
  - `obsidian`: Ensures seamless integration with the Obsidian API.
- **Runtime**:
  - `sse`: Manages server-sent events for response streaming.

## Commands
- **Chat**: Initiates a chat session from the current note.
- **Create New Chat with Highlighted Text**: Uses highlighted text to start a chat.
- **Create New Chat from Template**: Starts a chat using a predefined template.
- **Infer Title**: Generates a chat title based on conversation content.
- **Add Comment Block**: Inserts a comment block that is ignored by the plugin.
- **Clear Chat**: Deletes chat messages while preserving frontmatter.
- **Stop Streaming**: Stops a response mid-stream.

## Potential Improvements
- Enhance mobile compatibility.
- Introduce additional frontmatter customization options.
- Support alternative LLM providers.
- Improve performance for longer token limits.

## Notes
- Originally developed by Bram Adams, with a repository forked and maintained by Jason Nathan.
- The project is actively seeking maintainers (as of April 2024).
- The upstream repository remains accessible at `bramses/chatgpt-md`.

