# Counsel-Ai
Legal Question Answering (LQA) system tailored for law
## Project Overview

This project proposes the development of a Legal Question Answering (LQA) system tailored for law. The system will leverage a fine-tuned Large Language Model (LLM) trained on case law and statutory texts, ensuring accurate legal responses. A key feature of the system is citation verification, enhancing reliability by referencing relevant legal sources. The intended beneficiaries include paralegals, legal researchers, judges and non-lawyers seeking legal interpretability and case law research. The project aims to bridge the gap between complex legal documents and practical accessibility.

Dataset Description
The r/legal advice dataset, sourced from the Hugging Face Datasets Hub Pile of Law, is a collection of legal inquiries and community responses extracted from the r/legaladvice subreddit. The dataset is divided into a training set and a test set, both containing real-world legal questions along with user-generated responses. These discussions cover a diverse range of legal topics, including tenant landlord disputes, employment issues, contract law, and criminal defence.

### Challenges Faced During Fine-Tuning

- **Legal text ≠ Legal advice**: Statutes and regulations are written in a formal, non-conversational style, making it difficult for the model to learn how to interact naturally with users.
- **Lack of question-answer structure**: Legal documents rarely reflect real-world legal interactions, meaning there were no natural patterns of asking and answering legal questions to fine-tune on.
- **Highly referential format**: Laws often reference other sections abstractly (e.g., “§402(b)” or “Article 14(3)”) without providing full context, making them hard for models to understand without a retrieval system.
- **Low-quality responses**: Many publicly available comments were inaccurate, oversimplified, or speculative—unsuitable for responsible model behavior.
- **No legal credentials**: Much of the available advice came from non-professionals, undermining the goal of building a credible, trustworthy legal assistant.

Solution 

Distillation of knowledge from larger models to smaller models

I used a larger model (Gemini 2.0 Flash) to generate high-quality, safe, and legally grounded responses to real user-style questions.

Instead of generating free-form answers, I guided Gemini with external context specifically:

- Relevant excerpts from actual legal documents or statutes
- Prompts instructing the model to cite specific laws or sections in its response

This process allowed me to:

- Build a parallel corpus of realistic questions and legally sound, explainable answers
- Ensure responses were factually accurate and included legal citations
- Maintain consistency, clarity, and reliability for downstream fine-tuning
