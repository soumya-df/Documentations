# Data Façade Glossary

## 🤖 **Chat Agent**

**Chat Agent** It is like an assistant to you which consumes all the information, business context and logics of your organization in order to provide relevant insight of your queries through **chat** and help you out to get the correct insight.

## 📑**Default Application Context**

A setting in the **Chat Agent** of the **Data Façade** platform that enables users to define a broad **context** for responses. For example: it can be used to specify that all datetime columns are in IST and need to be converted to GMT.

## 🧑🏻‍💼**Business Context**

**Business context,** for a **Chat Agent**, means how it replies to certain words or questions. Think of it like teaching the agent to react in a certain way.

For example, in a retail organization, to figure out how many customers stop buying (called "churn rate"), you use specific tables and only look at "active" customers. Imagine the "active" customer means someone who shopped last month, which you add in business context along with the **business keyword** “churn rate”. Now, if someone asks about the "monthly churn rate," the agent knows to check those tables and only count the "active" shoppers to give the answer.

## 🗃️**Business Keyword**

In the context of a **Chat Agent**, a **business keyword** is a specific term or phrase related to a company's operations or industry. When this keyword is mentioned by the user, the **Chat Agent** uses predefined **business context** (like tables, instruction, or other formula) to provide a specific and relevant answer.

For instance, in the previous retail setup, "churn rate" is a **business keyword**. When a user asks about it, the agent refers to the **business context** set under this keyword.

## 💽**Data**

In the context of a **Chat Agent**, data refers to the selected tables used to calculate and provide answers to queries posed by users.

## 📤**Share with**

Letting your team members to input questions into the chat box and receive insights and answers derived from the organization's data. This collaborative feature enables users to collectively engage with the Chat Agent and benefit from the insights it provides.

## ✏️**Editors**

Individuals or users granted specific permissions to modify, configure, or update the **Chat Agent**'s **business context**, and table information to shape its responses and the insights it provides from the **organization's data**.

## 🎮**Playground**

A feature within the **Data Façade** platform where users can test, generate, and refine **scripts** using AI, ensuring they produce the desired output. It allows users to select a specific chat agent for **business context**, validate script results, and subsequently add successful scripts to the **Chat Agent**'s **training data**.

## 💬**Chat**

The interactive interface within the **Data Façade** platform where users pose questions or input queries, and the **Chat Agent** responds with relevant information or insights derived from the **organization's data**, based on its predefined **business context** and training.

## 🧑🏻‍🔧**Chat Agent training data**

 In the context of a **Chat Agent**, **training data** is like a study guide. It's a collection of questions and their correct answers (in the form of tested codes or scripts). This helps the **Chat Agent** learn and give the right responses when users ask similar questions later on.

## 🔎**Infer Table**

In the context of a **Chat Agent**, the **Infer Table** feature refers to the ability of the **Chat Agent** to automatically deduce or identify the necessary tables and columns required to compute or answer a query, based on the asked question and the given business context.

## 🛑**Strict Mode**

 In the context of a **Chat Agent**, **Strict Mode** is a feature that ensures the agent doesn't make assumptions or inferences from ambiguous or incomplete queries. Instead, it asks for clarification or more information to provide accurate and clear responses, rather than guessing or providing unclear or incorrect answers.