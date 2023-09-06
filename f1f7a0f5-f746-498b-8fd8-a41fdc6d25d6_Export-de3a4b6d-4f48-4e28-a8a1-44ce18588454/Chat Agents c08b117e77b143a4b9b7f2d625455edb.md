# Chat Agents

⌛**7 minutes read**

# What is Chat Agent?

Greetings, fellow data practitioners!

🤔Do you ever find yourself overwhelmed with ad-hoc questions from your business teams on a daily basis, taking away from your time to focus on deep analytics? What if I told you there is a solution to this problem?

😎Imagine having an assistant at your disposal that can address these questions for you. Moreover, if the assistant is designed to empower you by uncovering deeper insights autonomously, saving you time and effort. Think about how much more time you could allocate towards your deep analytics projects with this added support.

🤖The **Chat Agent** is like an assistant to you. It consumes all the information, business context, and logic that you provide to provide relevant insights to your queries through chat, helping you obtain the correct insights.

---

# Getting Started

Creating a chat agent is super easy. After landing on our homepage, click the "Agent" button to create one. 

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled.png)

<aside>
💡 Not sure about Chat Agents?  please refer our [**Onboarding Document**](https://www.notion.so/Onboarding-Document-7638ee64ac224389a739987a14f3a35d?pvs=21).

</aside>

Now let us walk you through how to create an efficient Chat Agent in Data Façade. 

Once you click on “**Create An Agent**”, you come up to Agent configuration page.

Setting up your agent is a breeze! Just provide the essentials: **Agent Name**, **Agent Description**, **Agent Default Context**, **Provider language** (SQL/Python), and select the tables you need by clicking the data button on the right. Once done, hit the "**Save Agent**" button and voila! You're ready to go!

<aside>
💡 Wondering what the above terms mean? You can consult our **[Glossary](https://www.notion.so/Data-Fa-ade-Glossary-e3699b0336774af389fbaae3e164b48d?pvs=21)**.

</aside>

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%201.png)

<aside>
💡 Wondering what does “Infer Table” and “Strict Mode” means? You can look at our **[Glossary](https://www.notion.so/Data-Fa-ade-Glossary-e3699b0336774af389fbaae3e164b48d?pvs=21)**.

</aside>

<aside>
💡 Wondering why we add “Do not consider ingest time for any calculation” in the **Agent Default Context**🤔? You may have heard of the "ingest time" in a database. It's a column that stores the timestamp or datetime when a particular piece of data was added to the database. But why make things complicated by considering such a column? 😃

</aside>

<aside>
💻 Want to use the same tables? Here is the link of [**demo data**](https://drive.google.com/drive/folders/19GQ3GSv88oLI8Oa5ckWXMOZSSKcuZ2XF?usp=sharing). You can also get the tables once you sync our default PostgreSQL provider

</aside>

---

# Get insight through chat

Once everything is ready, click on "**Preview**" and you can begin chatting with the agent. Kick off the conversation with a crucial yet straightforward question: "**How many customers completed purchases in July 2023?**"😎

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%202.png)

See, it is easy right?

<aside>
💬 Want to see the code generated in calculating the result?  Click on “**Edit & Train**”

</aside>

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%203.png)

<aside>
💡 Want to ask a follow-up question? Use the tag [followup] Before the question. For example:[followup] Show me the customer names. Although your agent is going to suggest few follow-up questing after every question, you can give that a try.

</aside>

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%204.png)

---

# Add business context through chat

Now you want to know some more on business metrics that you care about  “**How much profit and revenue is generated from these customers?**”. Let ask that through a followup.

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%205.png)

Hmmm🤔 interesting, the agent is asking for some clarification. Let’s “**Add Business Context**”

So here I clarify the question by adding **Business Keywords** (profit and revenue) and context

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%206.png)

<aside>
💡 Looking to know more about Business Context and Business Keywords? Look no further than our **[Glossary](https://www.notion.so/Data-Fa-ade-Glossary-e3699b0336774af389fbaae3e164b48d?pvs=21)**!

</aside>

```
revenue= sum(total amount)
profit = sum(total amount - tax)
```

<aside>
💡 **Do you want to know why?** Follow the table below. The "total amount" column shows the transaction amount, including tax. The "tax" column represents the total tax for that transaction.

</aside>

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%207.png)

Now, let's ask the same question again

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%208.png)

Great! The answer was smooth this time.

<aside>
💡 Want to know the explanation of the calculation? Just click on “**Explanation**” tab.

</aside>

---

# Get chart through chat

🤔 Wondering "**What is the revenue for different regions in July 2023?**"? Let's ask the agent.

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%209.png)

Great!! now let visualize it, got to “**Chart**” and see your agent already created a visualization

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%2010.png)

"**Save**" the chart to use it in creating a dashboard. Additionally, you can create your own chart by exploring the "**New Chart**" tab.

---

# Give clarification to agent through chat and save code to training data

Now you might want to know which gateway platform is famous in different region?

Let’s ask that “**Which payment gateway did most customers use for purchases in different regions during July 2023?**”

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%2011.png)

🤔Hmmm, the output doesn't seem to be correct. Why does the Europe region have three payment gateways? It should only have one, right? Let’s clarify it just click on 👎🏻 and a popup will come up.

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%2012.png)

write “**Only show the most used gateway for each region.**” in the box and click on “**Save And Submit**”.

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%2013.png)

See! It worked 🙌🏻. But you might be thinking, "Do I need to clarify every time I ask the same question?" The answer is no! 🚫

Simply click on "**Edit & Train**" and save the code. The code is now saved in your Chat Agent's training data. This means that every time you ask a similar question, you won't need to clarify. The Agent will handle it for you 😎.

<aside>
💡 While saving the code, the corresponding question is also saved. You can view both the code and the question by navigating to the "Business Context" page of the Agent.

</aside>

Still not sure? Try asking "**Which payment gateway did most customers use for purchases in different countries during July 2023?**" after following the above process 😃

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%2014.png)

![Untitled](https://github.com/soumya-df/Documentations/blob/main/f1f7a0f5-f746-498b-8fd8-a41fdc6d25d6_Export-de3a4b6d-4f48-4e28-a8a1-44ce18588454/Chat%20Agents%20c08b117e77b143a4b9b7f2d625455edb/Untitled%2015.png)

<aside>
💡 If you're curious about the meaning of "Training Data" in the context of a chat agent, check out our **[Glossary](https://www.notion.so/Data-Fa-ade-Glossary-e3699b0336774af389fbaae3e164b48d?pvs=21)**!

</aside>

[Data Façade Glossary](https://www.notion.so/Data-Fa-ade-Glossary-e3699b0336774af389fbaae3e164b48d?pvs=21)