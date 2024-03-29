# Perplexity Inspired LLM Deviaweb search

This repository contains the code and instructions needed to build a sophisticated search engine that leverages the capabilities of Groq, Mixtral, Langchain.JS, Brave Search, and OpenAI. Designed to efficiently return sources, answers, and follow-up questions based on user queries, this project is an ideal starting point for developers interested in natural language processing and search technologies.

## Technologies Used

- **Express.js**: A web application framework for Node.js, used to create server-side applications.
- **Body-Parser**: A middleware for Express.js, it's used to parse incoming request bodies before your handlers.
- **Groq & Mixtral**: Technologies for processing and understanding user queries.
- **Langchain.JS**: A JavaScript library focused on text operations, such as text splitting and embeddings.
- **Brave Search**: A privacy-focused search engine used for sourcing relevant content.
- **OpenAI**: Leveraged for generating coherent and contextually relevant answers and follow-up questions.
- **Cheerio**: Utilized for HTML parsing, allowing the extraction of content from web pages.

## Getting Started

### Prerequisites

- Ensure Node.js and npm are installed on your machine.
- Obtain API keys from Groq, OpenAI, and Brave Search.

### Obtaining API Keys

- **Groq API Key**: [Get your Groq API key here](https://console.groq.com/playground).
- **OpenAI API Key**: [Generate your OpenAI API key here](https://platform.openai.com/api-keys).
- **Brave Search API Key**: [Obtain your Brave Search API key here](https://api.search.brave.com/app/dashboard).

### Installation

1. Clone the repository:
    ```git clone https://github.com/ouic/web-search-llm.git```
2. cd into the directory
    ```cd web-search-llm```
3. Install the required dependencies:
    ```npm install```
    or 
     ```bun install```
4. Create a `.env` file in the root of your project and add your API keys:
    ```
    GROQ_API_KEY=<your_groq_api_key>
    BRAVE_SEARCH_API_KEY=<your_brave_search_api_key>
    OPENAI_API_KEY=<your_openai_api_key>
    ```

### Running the Server

To start the server, execute:
```npm start```
The server will be listening on port 8844.

## Usage

Make a POST request to `localhost:8844` with a JSON body containing your query and the desired parameters:

```
{
  "message": "Tell me the Anthropic's Claude 3",
  "returnSources": true,
  "returnFollowUpQuestions": true,
  "embedSourcesInLLMResponse": false,
  "textChunkSize": 800,
  "textChunkOverlap": 200,
  "numberOfSimilarityResults": 2,
  "numberOfPagesToScan": 4
}
```

The engine will process your query and return a comprehensive answer along with sources and, if requested, follow-up questions.


## Contributing

Contributions to the project are welcome. Feel free to fork the repository, make your changes, and submit a pull request. You can also open issues to suggest improvements or report bugs.

## License

This project is created by Deviaweb.

I'm the developer behind Deviaweb. If you find my work helpful or enjoy what I do, consider supporting me. Here are a few ways you can do that:

- **Website**: Check out my website at [deviaweb.fr](https://deviaweb.fr)
- **Github**: Follow me on GitHub at [github.com/ouic](https://github.com/ouic)