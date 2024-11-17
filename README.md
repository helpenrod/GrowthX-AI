# GrowthX-AI: AI Automation Challenge

## Reasoning for the Approach
### 1. Input: Website URL
The workflow begins by accepting a company website URL as input. This design choice aligns with the task's requirement of focusing on prospect companies. A URL serves as a rich source of data about the company, including its services, mission, and content.

### 2. Data Extraction
The script uses Python's requests library to fetch the web page and BeautifulSoup for HTML parsing. These tools are lightweight and effective for extracting structured data, such as:

* Title: Taken from the <title> tag, which usually contains the company name or tagline.
Description: Extracted from meta tags (meta[name="description"] or meta[property="og:description"]), providing a quick summary of the webpage content.
* Content: Text from <p> tags is aggregated to gather general context about the company.
This step ensures the workflow gathers diverse and meaningful data points from the website.

### 3. Content Summarization and Article Generation
The extracted data is passed to a GPT-Neo 2.7B text generation pipeline. The reasoning here is:

* Custom Prompts: The prompt explicitly instructs the model to create a concise article tailored to a sales audience. This specificity ensures relevance and brevity.
* Intermediate Reasoning: The model is guided to incorporate elements like the company’s title, description, and content into the output. By structuring the prompt, the model generates more coherent and goal-oriented responses.
* Model Choice: GPT-Neo was selected due to its accessibility and ability to generate coherent, domain-specific text with minimal tuning.
### 4. Output: Informative Article
The generated article is the final deliverable, summarizing the company’s key aspects for the sales team. This output format is concise yet detailed enough to equip the sales team with actionable insights.

### 5. Exporting Results
The workflow includes functionality to save the output as a .txt file. This ensures:

* Accessibility: The sales team can easily review and distribute the article.
* Reusability: The generated article can be archived or further processed.
