Article Link: 

# Methodology

We systematically tested eight generative search tools:
- OpenAI’s ChatGPT Search (4o) 
- Perplexity
- Perplexity Pro
- DeepSeek-V3 Search 
- Microsoft’s Copilot
- xAI’s Grok-2 
- xAI's Grok-3 (beta)
- Google’s Gemini (2.0 Flash)

## Publisher Selection
We chose 20 news publishers with varying stances on AI access that either permit search bots’ web crawlers via `robots.txt`, or block them. 

The Robot Exclusion Protocol (`robots.txt`) is a web standard that gives website publishers the option to “disallow” web crawlers—automated programs that systematically browse the internet to discover and retrieve content. Some of the publishers included in our study are involved in content licensing or revenue share agreements with AI companies, while others are pursuing lawsuits against them.

## Query Selection
We randomly selected 10 articles from each publisher and manually selected direct excerpts from those articles for use in our queries. 

After providing each chatbot with the selected excerpts, we asked them to identify the corresponding article’s:
1. Headline
2. Original publisher
3. Publication date
4. URL

The query format was as follows:
```
[insert excerpt from article]

-- 
Identify the article that contains this quote. Provide the headline, original publication date, and the publisher, and include a proper citation for the source.

```

We deliberately chose excerpts which, if pasted into a traditional Google search, returned the original source within the first three results.

## Testing Process
We ran a total of **1,600 queries**:
- **20 publishers** × **10 articles** × **8 chatbots**

We manually evaluated the chatbot responses based on three attributes:
1. **Correct article retrieval**
2. **Correct publisher identification**
3. **Correct URL retrieval**

## Data Fields Explanation

- **Tech Platform** – The generative search tool used 
- **Publication** – The news publisher from which the article originates 
- **Affiliation** – Whether the publisher has a deal/lawsuit with any AI company 
- **Crawler** – Indicates whether the publisher allows or blocks search bots via `robots.txt`.
- **Date of Article** – The original publication date of the article.
- **Paywalled Article?** – Whether the article is behind a paywall 
- **Source URL** – The original URL of the article.
- **Prompt** – The excerpt from the article used as a query for the chatbot.
- **Prompt Number** – A numerical identifier for the query.
- **Answer** – The chatbot's response to the query.
- **Answer: Publisher** – The publisher name identified by the chatbot.
- **Answer: Citation Link** – The URL cited by the chatbot as the source.
- **Answer: Date Listed** – The publication date retrieved by the chatbot.
- **Confidence** – The chatbot's confidence level in its response.
- **Proximity to Original Content** – How close the chatbot's response is to the original article.
- **Answer: Correct Article Identified?** – Whether the chatbot retrieved the correct article.
- **Answer: Correct Publisher?** – Whether the chatbot identified the correct publisher.
- **Answer: Correct Date?** – Whether the chatbot retrieved the correct publication date.
- **Answer: Correct URL Cited?** – Whether the chatbot provided the correct URL.
- **Correctness Score** – A final assessment of the chatbot’s accuracy in retrieving the correct information. See below for how we classified it.

### How Correctness Score was Categorized
Each response was categorized as follows:
- **Correct**: All three attributes were correct.
- **Correct but Incomplete**: Some attributes were correct, but the answer was missing information.
- **Partially Incorrect**: Some attributes were correct while others were incorrect.
- **Completely Incorrect**: All three attributes were incorrect and/or missing.
- **Not Provided**: No information was provided.

## **How to Access the Data File**

Follow these steps to decrypt and extract the dataset:

1. **Download the data file** to your local system.
2. **Navigate to the file location** in your terminal:

   ```bash
   cd [path_to_file]
   ```

3. **Decrypt the file using GPG** (you will be prompted for a password):

   ```bash
   gpg --output GenAISearch_Data.tar.gz --decrypt GenAISearch_Data.tar.gz.gpg
   ```

4. **Use the following password when prompted:**
   ```
   Qz8!pL4#XvG2@rT9KdY&
   ```

5. **Extract the contents of the decrypted archive:**

   ```bash
   tar -xvzf GenAISearch_Data.tar.gz
   ```

