# Hybrid Memory-Retrieval Model: Enhancing Trust in Medical Chatbot          





## About 

Large Language Models (LLMs) have shown promise in healthcare applications, yet their tendency to hallucinate and forget prior context remains a critical challenge, especially in medical dialogues where factual accuracy and contextual continuity are paramount. This project introduces a hybrid memory-retrieval architecture that enhances the reliability of medical chatbots by integrating Phi-2, a lightweight 2.7B parameter LLM, with two key retrieval strategies: Memory Retrieval (MR) using ChromaDB and Advanced Retrieval-Augmented Generation (RAG) via BM25, MedCPT, and Reciprocal Rank Fusion (RRF).

ChromaDB serves as a persistent memory store, capturing user-specific interaction history for contextual anchoring in follow-up queries. Meanwhile, Selective RAG performs real-time document retrieval across a unified corpus of over 216,000 medical QA pairs, combining lexical (BM25) and semantic (MedCPT) retrieval results to improve relevance and reduce noise. The merged memory and document contexts are fed into a structured prompt, optimized to fit within Phi-2’s token window. In scenarios where no relevant content is retrieved, the model safely defaults to a "no response" fallback, further mitigating hallucinations. Evaluation on the MedQuAD dataset shows that this hybrid system significantly outperforms traditional and fine-tuned RAG baselines. It achieves a BERTScore F1 of 0.8644, indicating strong semantic alignment with ground truth answers, while maintaining a lower latency (28s) than larger models. Though perplexity is higher (12.8758), this is attributed to longer and more informative outputs due to memory inclusion.

By combining structured memory with adaptive retrieval, this architecture delivers more fluent, grounded, and trustworthy responses, marking a step forward in safe, explainable AI for medical question answering.

