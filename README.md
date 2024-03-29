# Perplexity-Inspired LLM Deviaweb Search Engine

This repository contains the code and instructions needed to build a sophisticated search engine that leverages the capabilities of [Groq](https://www.groq.com/), [Mistral AI's Mixtral](https://mistral.ai/news/mixtral-of-experts/), [Langchain.JS](https://js.langchain.com/docs/), [Brave Search](https://search.brave.com/), [Serper API](https://serper.dev/), and [OpenAI](https://openai.com/). Designed to efficiently return sources, answers, images, videos, and follow-up questions based on user queries, this project is an ideal starting point for developers interested in natural language processing and search technologies.

## Technologies Used

- **Next.js**: A React framework for building server-side rendered and static web applications.
- **Tailwind CSS**: A utility-first CSS framework for rapidly building custom user interfaces.
- **Vercel AI SDK**: The Vercel AI SDK is a library for building AI-powered streaming text and chat UIs.
- **Groq & Mixtral**: Technologies for processing and understanding user queries.
- **Langchain.JS**: A JavaScript library focused on text operations, such as text splitting and embeddings.
- **Brave Search**: A privacy-focused search engine used for sourcing relevant content and images.
- **Serper API**: Used for fetching relevant video and image results based on the user's query.
- **OpenAI Embeddings**: Used for creating vector representations of text chunks.
- **Cheerio**: Utilized for HTML parsing, allowing the extraction of content from web pages.
- **Ollama (Optional)**: Used for streaming inference and embeddings.

## Getting Started

### Prerequisites

- Ensure Node.js and npm are installed on your machine.
- Obtain API keys from OpenAI, Groq, Brave Search, and Serper.

### Obtaining API Keys

- **OpenAI API Key**: [Generate your OpenAI API key here](https://platform.openai.com/account/api-keys).
- **Groq API Key**: [Get your Groq API key here](https://console.groq.com/keys).
- **Brave Search API Key**: [Obtain your Brave Search API key here](https://brave.com/search/api/).
- **Serper API Key**: [Get your Serper API key here](https://serper.dev/).

### Installation

1. Clone the repository:
    ```
    git clone https://github.com/ouic/deviaweb-search.git
    ```
2. Install the required dependencies:
    ```
    npm install
    ```
    or
    ```
    bun install
    ```
3. Create a `.env` file in the root of your project and add your API keys:
    ```
    OPENAI_API_KEY=your_openai_api_key
    GROQ_API_KEY=your_groq_api_key
    BRAVE_SEARCH_API_KEY=your_brave_search_api_key
    SERPER_API=your_serper_api_key
    ```

### Running the Server

To start the server, execute:
```
npm run dev
```
or
```
bun run dev
```

the server will be listening on the 8844 port.

## Editing the Configuration

The configuration file is located in the `app/config.tsx` file. You can modify the following values

- useOllamaInference: false,
- useOllamaEmbeddings: false,
- inferenceModel: 'mixtral-8x7b-32768',
- inferenceAPIKey: process.env.GROQ_API_KEY,
- embeddingsModel: 'text-embedding-3-small',
- textChunkSize: 800,
- textChunkOverlap: 200,
- numberOfSimilarityResults: 2,
- numberOfPagesToScan: 10,
- nonOllamaBaseURL: 'https://api.groq.com/openai/v1'

### Ollama Support (Partially supported)
Currently, streaming text responses are supported for Ollama, but follow-up questions are not yet supported.

Embeddings are supported, however, time-to-first-token can be quite long when using both a local embedding model as well as a local model for the streaming inference. I recommend decreasing a number of the RAG values specified in the `app/config.tsx` file to decrease the time-to-first-token when using Ollama.

To get started, make sure you have the Ollama running model on your local machine and set within the config the model you would like to use and set use OllamaInference and/or useOllamaEmbeddings to true.

Note: When 'useOllamaInference' is set to true, the model will be used for both text generation, but it will skip the follow-up questions inference step when using Ollama.

More info: https://ollama.com/blog/openai-compatibility

## Contributing

Contributions to the project are welcome. Feel free to fork the repository, make your changes, and submit a pull request. You can also open issues to suggest improvements or report bugs.


## License

This project is opensource.

I'm the developer behind Deviaweb. If you find my work helpful or enjoy what I do, consider supporting me. Here are a few ways you can do that:

- **Website**: Check out my website at [deviaweb.fr](https://deviaweb.fr)
- **Github**: Follow me on GitHub at [github.com/ouic](https://github.com/ouic)
