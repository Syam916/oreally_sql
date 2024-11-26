# Introduction
 
Welcome to the architectural story of ShopWise Assistant – the O'Reilly Winter 2024 Architectural Kata.
 
This challenge invites participants to design and build an AI-powered support assistant for ShopWise Solutions, blending advanced natural language understanding, seamless database integration, and user-centric features to create a cutting-edge customer service solution.
 
---
 
# Company Overview
 
Embark on a transformative data journey with **Vardaan Pioneering Data Sciences**—where innovation maximizes data potential, optimizing operations and streamlining processes for data-driven decision-making.

![Vardaan Data Sciences Logo](https://github.com/Syam916/oreally_sql/blob/master/vds%20(2).png)
 
Dedicated to knowledge-sharing, our training programs provide practical skills in the ever-changing world of data sciences. As a consultancy, we bridge the gap between raw data and actionable insights, delivering trends analysis and dashboards using advanced analytics, machine learning, and AI. Welcome to a future where **Vardaan Data Sciences Service** shapes a transformative path for organizations in the digital age.

---

**ShopWise Solutions** is a dynamic e-commerce website specializing in electronics and gadgets. Offering a wide range of high-quality products, from the latest smartphones and laptops to cutting-edge smart home devices and accessories, ShopWise caters to tech enthusiasts and everyday consumers alike. The platform focuses on providing a seamless shopping experience with detailed product descriptions, personalized recommendations, and robust customer support. With its commitment to innovation and user satisfaction, ShopWise Solutions stands as a go-to destination for all things tech in the online marketplace.
 
---
 
# Problem Statement
 
The problem statement for the ShopWise Assistant competition revolves around developing an AI-powered support assistant to enhance customer interactions on ShopWise Solutions, an e-commerce platform specializing in electronics and gadgets. The assistant must efficiently handle customer inquiries about products, such as descriptions, comparisons, availability, and recommendations, as well as manage order-related queries, including tracking, status updates, history, return eligibility, and shipping updates. It should seamlessly integrate with ShopWise’s databases to provide accurate, real-time responses while avoiding inaccuracies or fabricated information. The solution should support multi-turn conversations for handling complex queries and deliver personalized interactions based on customer data. Additionally, the assistant must ensure a smooth and fast user experience, with scalable and reliable deployment, aligning with ShopWise's goals of improving customer engagement and satisfaction.

![logo](https://github.com/Syam916/oreally_sql/blob/master/image%20(1).png)
 
 
The website for **ShopWise Solution** is a sleek and user-friendly e-commerce platform. It is designed to provide a seamless shopping experience with a modern interface. Key features include: 
 
1. **Header Navigation**: 
   - A prominently displayed header features the brand logo, a search bar for easy product discovery, and navigation links to key sections like "Home," "About," "Products," "My Account," and "Cart."
 
2. **Interactive Chatbot**: 
   - A chatbot icon in the bottom right corner provides real-time assistance, improving customer support and engagement by addressing queries or guiding users through the website.
 
---
 
# Context View
 
The workflow of the ShopWise Chatbot is outlined in the steps below:
 
1. **Start**: 
   - The process begins with initializing the workflow.
 
2. **Data Cleaning**: 
   - The chatbot's system preprocesses the input data using tools like Pandas to ensure the data is clean and structured properly.
 
3. **Prompt Input**: 
   - A user provides a prompt or query to the chatbot as input, which initiates the processing.
 
4. **LLM Model Processing**: 
   - The prompt is processed using a Gemini Pro LLM (Large Language Model) to analyze the query. This step involves determining whether the input prompt is valid and related to the existing data.
 
   - **If the prompt is valid and related**: 
     - The system converts the prompt into an SQL query for retrieving or manipulating database records.
   - **If the prompt is not related to the data**: 
     - The system identifies this mismatch and notifies the user that the given prompt does not align with the available data, prompting for revalidation or rephrasing.
 
5. **SQL Query Conversion**: 
   - Valid prompts are converted into SQL queries to fetch or process information from the database effectively.
 
6. **RAG Enhancement**: 
   - After retrieving the data, the system employs a RAG (Retrieval-Augmented Generation) mechanism to enhance the quality of the generated text response. This ensures the response is coherent, accurate, and relevant.
 
7. **Response Generation**: 
   - The enhanced response is provided to the user in a clear and understandable format.
 
8. **End**: 
   - The process concludes with the chatbot delivering the final response to the user.
 
This workflow ensures accuracy, relevance, and high-quality interaction, making the chatbot efficient for user queries.
 
---
 
# Architecture
 
The AI-Powered Chatbot Architecture is designed for a seamless user experience in a customer service system. Below is the description of its components and workflow:
 
1. **User Interaction**:
   - The user starts by selecting a language.
   - The user enters a query, which is sent to the server for processing.
 
2. **Server and Chatbot**:
   - The server forwards the query to the chatbot system.
   - Inside the chatbot, several components work to process the query:
     - **Encode and Decode Data**: Prepares the input query for processing and decodes the output for a response.
     - **Tokenization**: Breaks the input into smaller meaningful units (tokens) for processing.
     - **Wordnet Model**: Utilizes a lexical database (such as WordNet) for understanding word meanings and relationships.
     - **Sentence Similarity Check**: Analyzes the similarity between user input and pre-existing data or knowledge base to provide the best match.
 
3. **Database**:
   - The chatbot interacts with a database to fetch or store information needed for responding to queries or improving the system.
 
4. **Response Flow**:
   - After processing, the chatbot generates potential responses, which are passed to a **Response Selector**.
   - The **Response Selector** determines the final response to send back to the user.
 
5. **Feedback Loop**:
   - If the response is invalid or unsatisfactory, the user can send feedback to the system. This feedback is processed to enhance the chatbot's performance.
 
Overall, the architecture illustrates the end-to-end workflow of a chatbot system, from user input to response delivery, including backend components like tokenization, similarity checks, and feedback integration.
 
---
