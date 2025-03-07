# llm-tools
testing experimenting llm tools
# Experiments with Memory for LLMs using LangChain and Persistence

This repository contains a series of experiments exploring different memory management strategies for large language models (LLMs) built with LangChain. The focus is on how to persist conversation history between sessions, optimize token usage, and enhance conversational context. These experiments demonstrate various techniques—from storing the complete dialogue to applying sliding windows and summarization—to build more context-aware and persistent chatbot applications.

## Overview of Experiments

Below is a summary of the experiments included in this repository:

1. **Full Conversation Persistence with ConversationBufferMemory**  
   - **Description:** In this experiment, the complete conversation history is stored and reloaded between sessions using `ConversationBufferMemory`.  
   - **Key Features:**  
     - Persists all interactions to a JSON file.  
     - Loads the full history on startup.  
     - Ideal for applications that require complete context.
   
2. **Sliding Window Memory with ConversationBufferWindowMemory**  
   - **Description:** This experiment demonstrates using a windowed memory approach where only the most recent *k* exchanges are retained.  
   - **Key Features:**  
     - Limits context to a fixed number of messages.  
     - Helps manage token consumption for long conversations.
   
3. **Summarized Memory with ConversationSummaryMemory**  
   - **Description:** To tackle token limitations for very long conversations, this experiment uses a summarization approach that compiles past interactions into a concise summary.  
   - **Key Features:**  
     - Uses an LLM to generate a running summary of the conversation.  
     - Balances between retaining essential context and controlling token usage.
   
4. **Additional Experiments (Planned/Future Work):**  
   - **Entity Memory:** Explore how to store and recall specific entities mentioned in the conversation.  
   - **Vector Store Memory:** Investigate storing conversation history in a vector database for retrieval-augmented generation (RAG) scenarios.

## Repository Structure

- **`experiment_1_buffer_memory.py`**  
  Contains the implementation of full conversation persistence using `ConversationBufferMemory`.

- **`experiment_2_window_memory.py`**  
  Demonstrates using a sliding window memory with `ConversationBufferWindowMemory`.

- **`experiment_3_summary_memory.py`**  
  Implements conversation summarization using `ConversationSummaryMemory` (or a variant) along with persistence.

- **`README.md`**  
  This file provides an overview of the experiments and usage instructions.

- **`requirements.txt`**  
  Lists the necessary dependencies (e.g., LangChain, OpenAI SDK, etc.).

## Getting Started

### Prerequisites

- Python 3.8 or higher
- An API key for your chosen LLM provider (e.g., OpenAI)
- Required packages listed in `requirements.txt`

### Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/llm-memory-experiments.git
   cd llm-memory-experiments
