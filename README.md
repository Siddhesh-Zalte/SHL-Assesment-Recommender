> **SHL** **Assessment** **Recommender** **–** **Project** **Approach**
> **Document**
>
> **by** **Siddhesh** **Zalte(MIT** **ADT** **University** **Pune)**
>
> **<u>Objective:</u>**
>
> Hiring managers often struggle to identify suitable assessments from a
> large catalog. The goal was to build an AI-powered recommendation
> engine that can understand job descriptions (via text or URL) and
> return the most relevant SHL assessments with useful metadata
>
> **<u>Approach:</u>**
>
> **1.** **Input** **handling**
>
> Users can input either a job description in plain text or provide a
> URL containing the job description.
>
> If URL is provided, the content is scraped using ***requests*** and
> ***BeautifulSoup*** to extract raw text for further processing.
>
> **2.** **LLM** **Integration(Gemini** **API)**
>
> Google Gemini Pro **(*google-generativeai*)** is used to analyze the
> job description
>
> A custom prompt ensures that model returns JSON array with 6 key
> attributes for each assessment.
>
>  Assessment Name
>
>  URL(link to SHL Product catalog)  Remote Testing Support
>
>  Adaptive/IRT support  Duration
>
>  Test type
>
> 3\. **Output** **Validation**
>
> Validated recommendations are displayed in a clean table using
> **Streamlit's** **st.table** and **pandas.DataFrame.** Only valid
> recommendations are displayed in formatted table using **Streamlit.**
> JSON response is also displayed on streamlit app.
>
> **4.** **Catalog** **Scraper**
>
> Added a built-in scrapper to fetch raw data and links from SHL’s
> official product catalog page. Extracted page text and all outbound
> links are displayed using expandable panels. This can assist in
> verifying the Gemini-generated URLs and expanding future automation.
>
> **<u>Tools Used:</u>**
>
>  **Frontend/UI:** Streamlit  **Backend:** Python
>
>  **LLM:** Google Gemini API
>
>  **Web** **Scrapping:** BeautifulSoup, requests  **Data**
> **Handling:** pandas, JSON
>
> **<u>Deployment:</u>**
>
> The app is designed to run as ***Streamlit*** ***app.*** Dependencies
> include ***google.generativeai,*** ***pandas,*** ***requests,*** and
> beautifulsoup4. For Delpoyment on Streamlit Cloud, the
> *requirements*.txt file must list all libraries, and the
> ***GOOGLE_API_KEY*** *should* *be* *configured.*
