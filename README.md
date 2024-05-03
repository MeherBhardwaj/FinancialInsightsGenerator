# Financial Insights Generator

The financial insights generator, is a simple app that involves the use of **Retrieval Augmented Generation.** It enables the user to select a company from the dropdown list available on the homepage, and submit it. Once submitted, the application will download all the SEC 10-K filings of that company, since 1995. This data will then be provided to Llama LLM which will then produce insights based on this data. 
For this project we primarily focus on four areas - The cash flow of the company in the latest year, the profit margins and return ratios, potential risks faced by the company, and its future outlook.
While further insights like revenue patterns and description of the products and services offered by the company can also be generated, It is believed that the above mentioned four areas would cover a good amount of information for a user that may be inclined to invest in the company.
## Installation
1) The app can be executed entirely on Google Colab based on the python notebook provided, However if the on premise infrastructure has better specifications, It is strongly advised to run the app on the local machine. This would reduce the execution time depending on how high the GPU power is and thus would generate insights much faster.
2) For on-premise / local machine execution, the dependencies mentioned in the **requirements.txt** document must be installed.
3) Authorization tokens have to be generated to use the model. These would involve a **hugging-face token** (along with the permission to use the llama library), as well as the **ngrok token**. However if the application is being run on the local machine, the second one becomes obsolete. 
## Features
1) The application involves a RAG system, which successfully generates up-to-date information effectively.
2) The application offers rudimentary knowledge for an investor to make the decision if they should proceed with exploring the financials or should choose a different company. Based on the requirements the prompts in the backend can be tweaked appropriately to make it suitable for investors at various levels.

## Other relevant points
1) The backend contains four prompts that appeared relevant to the scope of this project. However, these prompts can be tweaked, and more prompts can be added to generate insights based on other use-cases.
2) The results page is just a simple page containing insights. However, this can be further enhanced to make it user interactive.
## Justification behind the implemented logic
- **Not Using an API based LLM-** While this decision was not made deliberately at first, this turned out to be beneficial for the developer. API based LLMs tend to rely on their own server capacity while giving only limited free credits to the developer. This did not turn out well during the development of the application, as the credits either kept getting exhausted, or the API requests would not be responded well. After trying out multiple API providers, it was decided to go for a pre-trained model instead. While this came up with its own challenges, like higher response time and intense use of resources, It gives the liberty to the developer to decide generation factors like temperature etc. which can be used to generate more appropriate responses. Further, the application would not be dependent of the API provider's server's load or condition.
- **Tech Stack used-** The tech stack used is based on python3 language. We use a backend RAG system written in python3, and implement it on a Flask server. For the frontend, we use basic HTML and CSS. Since python3 provides support to various libraries and modules relevant to this project, as well as efficiently builds an RAG pipeline which lies at the heart of this project, it seemed like the correct choice. Flask server was used as it is easily compatible with Python3 language. Basic HTML and CSS were used since the objective of the project was to create a system that successfully generates insights, and that could be achieved without a fancy, interactive frontend.
- **Prompts selected for the task-** The idea behind the project was to generate financial insights for a user who might want to invest in the selected company. During its execution, we were brought to a trade-off. We want to generate as many insights as possible so that the user can effectively learn about the company's financials; However, we also attempt to not make the results page appear verbose. To cater to these problems, without making the results page complicated, It was decided to focus on four major areas-
- - **Financial health-**  To achieve this task, the insights about the cash flow of the company were chosen over the revenue trends, because cash flow depicts a better picture about the actual dispersion of money in the company. 
- - **Profits and Return ratios-** This is needed to show if the company is burning through cash or is actually profitable. Further, return ratios like return on equity and return on assets show how much return the company gets against its assets and the equity it diluted. This would help the potential investor to understand how his investment might get affected over time.
- - **Potential Risks-** This deals with the potential risks that the company is facing, or might face in the future. This helps in painting a fair picture about the risks involved in investing in that company.
- - **Future Outlook-** This is used to tell the potential investors about what the board members and other decision makers feel about the company's future and where they want to put their focus on.
- While the number of insights can be further increased to generate a plethora of information, The above four points should adequately cover the insights needed based on the scope of this project, without making the results verbose. 


## Contact

For feedback, queries or collaboration, contact- 
**Meher Bhardwaj** - bhardwajmeher01@gmail.com
